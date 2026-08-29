## Descripcion
I accidentally wrote the flag down. Good thing I deleted it!
## Solucion

```
celeh127-academy@webshell:~$ wget https://artifacts.picoctf.net/c_titan/76/challenge.zip
--2026-08-29 22:44:11--  https://artifacts.picoctf.net/c_titan/76/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.95, 3.160.5.18, 3.160.5.40, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.95|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19201 (19K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                         100%[=========================================================================>]  18.75K  --.-KB/s    in 0.005s  

2026-08-29 22:44:11 (3.45 MB/s) - 'challenge.zip' saved [19201/19201]

celeh127-academy@webshell:~$ unzip -q challenge.zip
celeh127-academy@webshell:~$ cd drop-in
celeh127-academy@webshell:~/drop-in$ git log -p
```

```
commit a6dca68e4310585eac3b5c9caf0f75967dfe972c (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:06 2024 +0000

    remove sensitive info

diff --git a/message.txt b/message.txt
index d263841..d552d1e 100644
--- a/message.txt
+++ b/message.txt
@@ -1 +1 @@
-picoCTF{s@n1t1z3_7246792d}
+TOP SECRET

commit e720dc26a1a55405fbdf4d338d465335c439fb3e
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:06 2024 +0000

    create flag

diff --git a/message.txt b/message.txt
new file mode 100644
index 0000000..d263841
--- /dev/null
+++ b/message.txt
@@ -0,0 +1 @@
+picoCTF{s@n1t1z3_7246792d}
(END)
```
## Notas adicionales
## Referencias
