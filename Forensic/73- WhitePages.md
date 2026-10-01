## Descripcion

I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://challenge-files.cylabacademy.net/library/4a463561643f2cc25e74665dadd7ca654a9b828dc7a5b9239a8000ab4179c57e/whitepages.txt) is all blank!
## Solucion

┌──(celesteh㉿K-Celeste)-[~/whitepages]
└─$ wget https://challenge-files.cylabacademy.net/library/4a463561643f2cc25e74665dadd7ca654a9b828dc7a5b9239a8000ab4179c57e/whitepages.txt

┌──(celesteh㉿K-Celeste)-[~/whitepages]
└─$ nano resolver.py

┌──(celesteh㉿K-Celeste)-[~/whitepages]
└─$ python3 resolver.py
'\u2003\u2003\u2003\u2003 \u2003 \u2003\u2003  \u2003\u2003\u2003\u2003 \u2003  \u2003\u2003\u2003  \u2003  \u2003\u2003\u2003\u2003 \u2003  \u2003\u2003 \u2003\u2003\u2003  \u2003\u2003 \u2003 \u2003  \u2003  \u2003 \u2003    \u2003\u2003 \u2003\u2003\u2003\u2003 \u2003 \u2003\u2003\u2003\u2003\u2003 \u2003 \u2003\u2003 \u2003 \u2003\u2003  \u2003 \u2003\u2003\u2003 \u2003 \u2003 \u2003\u2003'

┌──(celesteh㉿K-Celeste)-[~/whitepages]
└─$ nano resolver.py

```
with open("whitepages.txt", "r", encoding="utf-8") as f:
  content = f.read()
binary_string = ""
for char in content:
  if char == "\u2003":
    binary_string += "0"
  elif char == " ":
    binary_string += "1"

flag = ""
for i in range(0, len(binary_string), 8):
  byte = binary_string[i : i + 8]
  if len(byte) == 8:
    flag += chr(int(byte, 2))

print("Texto decodificado:")
print(flag)

```

┌──(celesteh㉿K-Celeste)-[~/whitepages]
└─$ python3 resolver.py
Texto decodificado:

academy

SEE PUBLIC RECORDS & BACKGROUND REPORT
5000 Forbes Ave, Pittsburgh, PA 15213
academy{not_all_spaces_are_created_equal_743510e5f5459071ed7d4109b7832a8e}

## Notas adicionales
## Referencias
