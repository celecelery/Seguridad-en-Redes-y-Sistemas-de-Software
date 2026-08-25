## Descripcion
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames.
## Solucion

```
celeh127-academy@webshell:~$ wget https://challenge-files.picoctf.net/c_wily_courier/730d9106a6ce1d52c6463b90937ec89f5eb661388954fbd15cfa0c8a2eec012f/Addadshashanammu.zip
--2026-08-24 17:18:41--  https://challenge-files.picoctf.net/c_wily_courier/730d9106a6ce1d52c6463b90937ec89f5eb661388954fbd15cfa0c8a2eec012f/Addadshashanammu.zip
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.160.5.18, 3.160.5.64, 3.160.5.95, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.160.5.18|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 5166 (5.0K) [application/octet-stream]
Saving to: 'Addadshashanammu.zip'

Addadshashanammu.zip 100%[===================>]   5.04K  --.-KB/s    in 0s      

2026-08-24 17:18:41 (100 MB/s) - 'Addadshashanammu.zip' saved [5166/5166]

celeh127-academy@webshell:~$ strings Addadshashanammu.zip | grip pico
-bash: grip: command not found
celeh127-academy@webshell:~$ strings Addadshashanammu.zip | grep pico
printf("*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_fc588427}\n");
celeh127-academy@webshell:~$ 
```
## Notas adicionales

ctrl a va a l inico de la linea de comando
ctrl e va al final de la linea de comando
## Referencias
