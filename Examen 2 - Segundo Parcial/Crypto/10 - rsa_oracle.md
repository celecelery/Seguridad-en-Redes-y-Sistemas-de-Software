## Descripcion
Can you abuse the oracle?

An attacker was able to intercept communications between a bank and a fintech company. They managed to get the [message](https://challenge-files.cylabacademy.net/library/f0397680c3aded57020481e88d04d8849fa29a48a8150a23c851942cd67f8389/secret.enc) (ciphertext) and the [password](https://challenge-files.cylabacademy.net/library/f0397680c3aded57020481e88d04d8849fa29a48a8150a23c851942cd67f8389/password.enc) that was used to encrypt the message.
## Solucion
usar script: 
```
import socket, re, subprocess

# 1. Cargar ciphertext objetivo
with open("password.enc") as f:
    c_target = int(f.read().strip())

# 2. Conectar al oráculo
s = socket.create_connection(("<HOST>", <PUERTO>), timeout=10)

def recv_until(target):
    buf = b""
    while target not in buf:
        d = s.recv(1024)
        if not d:
            break
        buf += d
    return buf.decode(errors="replace")

# Esperar menú y cifrar \x02
recv_until(b"decrypt.")
s.sendall(b"E\n")
recv_until(b"keysize):")
s.sendall(b"\x02\n")

out = recv_until(b"decrypt.")
c2 = int(re.search(r"ciphertext \(m \^ e mod n\) (\d+)", out).group(1))

# Descifrar ciphertext multiplicado (cegado)
c_blind = c_target * c2
s.sendall(b"D\n")
recv_until(b"Enter text to decrypt:")
s.sendall(f"{c_blind}\n".encode())

resp = recv_until(b"decrypt.")
s.close()

# Extraer 2P y despejar P
m2_hex = re.search(r"decrypted ciphertext as hex \(c \^ d mod n\): ([0-9a-fA-F]+)", resp).group(1)
m2 = int(m2_hex, 16)
p_int = m2 // 2
password = bytes.fromhex(hex(p_int)[2:]).decode()
print("Contraseña recuperada:", password)

# Descifrar secret.enc con openssl
res = subprocess.run(
    ["openssl", "enc", "-aes-256-cbc", "-d", "-in", "secret.enc", "-pass", f"pass:{password}"],
    capture_output=True, text=True
)
print("Contenido descifrado:", res.stdout)
```

flag: academy{su((3ss_(r@ck1ng_r3@_4263a53c}
## Notas adicionales
## Referencias
