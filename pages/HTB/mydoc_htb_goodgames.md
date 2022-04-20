---
title: HTB - GoodGames
tags: [laboratorio, HackTheBox]
keywords: laboratorio, hackthebox
summary: "Maquina GoodGames de hack the box"
sidebar: mydoc_sidebar
permalink: mydoc_htb_goodgames.html
folder: mydoc
topnav: topnav
---

## **Nivel 0**
{% include objetivo.html content="Debemos conectarnos al laboratorio mediante una conexion SSH. <br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→ Host:** bandit.labs.overthewire.org<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→ Puerto:** 2220<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→ Usuario:** bandit0<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→ Contraseña:** bandit0<br/>
" %}
{% include comandos.html content="ssh" %}
{% include callout.html content="Para conectarme mediante ssh solo necesito saber que el comando **ssh** funciona de la siguiente manera:<br/>&nbsp;&nbsp;&nbsp;&nbsp;→	ssh usuario@[host] -p [puerto]<br/>**Ejemplo:** ssh admin@mi.conexion.org -p 2222" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
ssh bandit0@bandit.labs.overthewire.org -p 2220<br/>
bandit0@bandit.labs.overthewire.org's password: bandit0<br/>
bandit0@bandit:~$
</div>
<br/>

## **Nivel 0 → Nivel 1**
{% include objetivo.html content="La contraseña del siguiente nivel esta almacenada en un archivo llamado **readme** localizado en el directorio **home**." %}
{% include comandos.html content="ls, cat" %}
{% include callout.html content="Realizo un **ls** para ver el contenido de la carpeta y un **cat [archivo]** para imprimir el contenido del archivo:" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit0@bandit.labs.overthewire.org -p 2220<br/>
bandit0@bandit:~$ ls<br/>
readme<br/>
bandit0@bandit:~$ cat readme<br/>
boJ9jbbUNNfktd78OOpsqOltutMc3MY1
</div>
{% include solucion.html content="boJ9jbbUNNfktd78OOpsqOltutMc3MY1" %}

## **Nivel 1 → Nivel 2**
{% include objetivo.html content="La contraseña del siguiente nivel esta almacenada en un archivo llamado **-** localizado en el directorio **home**." %}
{% include comandos.html content="ls, cat" %}
{% include callout.html content="Hago un **ls** para ver el contenido de la carpeta y un **cat ./[archivo]** para imprimir el contenido del archivo:" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit1@bandit.labs.overthewire.org -p 2220<br/>
bandit1@bandit:~$ ls<br/>
-<br/>
bandit1@bandit:~$ cat ./-<br/>
CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9<br/>
</div>
{% include solucion.html content="CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9" %}

## **Nivel 2 → Nivel 3**
{% include objetivo.html content="La contraseña del siguiente nivel esta almacenada en un archivo llamado **spaces in this filename** localizado en el directorio **home**." %}
{% include comandos.html content="ls, cat" %}
{% include callout.html content="Hago un **ls** para ver el contenido de la carpeta y un **cat 'archivo'** para imprimir el contenido del archivo:" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit2@bandit.labs.overthewire.org -p 2220<br/>
bandit2@bandit:~$ ls<br/>
spaces in this filename<br/>
bandit2@bandit:~$ cat "spaces in this filename"<br/>
UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK<br/>
</div>
{% include solucion.html content="UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK" %}

## **Nivel 3 → Nivel 4**
{% include objetivo.html content="La contraseña del siguiente nivel esta almacenada en un archivo oculto localizado en el directorio **inhere**." %}
{% include comandos.html content="ls, cat" %}
{% include callout.html content="Hago un **ls -la** para ver el contenido oculto de la carpeta y un **cat 'direccion_archivo'** para imprimir el contenido del archivo:" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit3@bandit.labs.overthewire.org -p 2220<br/>
bandit3@bandit:~$ ls -la inhere/<br/>
total 12<br/>
drwxr-xr-x 2 root    root    4096 May  7  2020 .<br/>
drwxr-xr-x 3 root    root    4096 May  7  2020 ..<br/>
-rw-r----- 1 bandit4 bandit3   33 May  7  2020 .hidden<br/>
bandit3@bandit:~$ cat inhere/.hidden <br/>
pIwrPrtPN36QITSp3EQaw936yaFoFgAB<br/>
</div>
{% include solucion.html content="pIwrPrtPN36QITSp3EQaw936yaFoFgAB" %}

## **Nivel 4 → Nivel 5**
{% include objetivo.html content="La contraseña del siguiente nivel esta almacenada en un archivo legible por humanos en el directorio **inhere**." %}
{% include comandos.html content="ls, cat, file" %}
{% include callout.html content="Hago un **ls** para ver el contenido de la carpeta y un **file inhere/*** para ver los tipos de archivos. Una vez que ya se que archivo necesito, uso un **cat** para ver su contenido:" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit4@bandit.labs.overthewire.org -p 2220<br/>
bandit4@bandit:~$ ls inhere/<br/>
-file00  -file02  -file04  -file06  -file08<br/>
-file01  -file03  -file05  -file07  -file09<br/>
bandit4@bandit:~$ file inhere/*<br/>
inhere/-file00: data<br/>
inhere/-file01: data<br/>
inhere/-file02: data<br/>
inhere/-file03: data<br/>
inhere/-file04: data<br/>
inhere/-file05: data<br/>
inhere/-file06: data<br/>
inhere/-file07: ASCII text<br/>
inhere/-file08: data<br/>
inhere/-file09: data<br/>
bandit4@bandit:~$ cat inhere/-file07<br/>
koReBOKuIDDepwhWk7jZC0RTdopnAYKh<br/>
</div>

## **Nivel 5 → Nivel 6**
{% include objetivo.html content="La contraseña para el siguiente nivel esta alojada en un archivo en alguna parte del directorio **inhere** y tiene las siguientes propiedades:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→** Legible por humanos<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→** 1033 bytes de tamaño<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→** No ejecutable<br/>" %}
{% include comandos.html content="ls, cat, find" %}
{% include callout.html content="Hago un **ls** para ver el contenido del fichero **inhere**. Para buscar el archivo uso el comando **find** con los parámetros **-type f** y **-size 1033c**.<br/><br/>Con el parámetro **-type f** le decimos que tiene que ser un archivo.<br/><br/>Con el parámetro **-size 1033c** le indicamos que tiene un peso de 1033 bytes" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit5@bandit.labs.overthewire.org -p 2220<br/>
bandit5@bandit:~$ ls<br/>
inhere<br/>
bandit5@bandit:~$ find inhere/* -type f -size 1033c<br/>
inhere/maybehere07/.file2<br/>
bandit5@bandit:~$ cat inhere/maybehere07/.file2<br/>
DXjZPULLxYr17uwoI01bNLQbtFemEgo7<br/>
</div>

{% include solucion.html content="DXjZPULLxYr17uwoI01bNLQbtFemEgo7" %}

## **Nivel 6 → Nivel 7**
{% include objetivo.html content="La contraseña para el siguiente nivel esta alojada en un algún lugar del servidor y tiene las siguientes propiedades:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→** Usuario propietario: bandit7<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→** Grupo propietario: bandit6<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**→** Tamaño 33 bytes<br/>" %}
{% include comandos.html content="cat, find" %}
{% include callout.html content="Uso el comando find con los parámetros **-user**, **-group** y **size**. Además le añado **2>/dev/null** para desviar los fallos y que no se impriman por pantalla<br/><br/>Con el parámetro **-user** le decimos el usuario propietario del archivo.<br/><br/>Con el parámetro **-group** le indicamos el grupo propietario del archivo." type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit6@bandit.labs.overthewire.org -p 2220<br/>
bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null<br/>
/var/lib/dpkg/info/bandit7.password<br/>
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password<br/>
HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs<br/>
</div>
{% include solucion.html content="HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs" %}

## **Nivel 7 → Nivel 8**
{% include objetivo.html content="La contraseña esta alojada en un archivo llamado **data.txt**, al lado de la palabra **millionth**" %}
{% include comandos.html content="ls, grep" %}
{% include callout.html content="Con el comando **grep** podemos buscar lineas de texto en un archivo. Lo uso de la siguiente manera: <br/><br/>&nbsp;&nbsp;&nbsp;&nbsp;**grep** [palabra_a_buscar] [archivo]" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit7@bandit.labs.overthewire.org -p 2220<br/>
bandit7@bandit:~$ ls<br/>
data.txt<br/>
bandit7@bandit:~$ grep millionth data.txt<br/>
millionth	cvX2JJa4CFALtqS87jk27qwqGhBM9plV<br/>
</div>
{% include solucion.html content="cvX2JJa4CFALtqS87jk27qwqGhBM9plV" %}

## **Nivel 8 → Nivel 9**
{% include objetivo.html content="La contraseña esta alojada en un archivo llamado **data.txt**. Es la única línea que solo se repite una vez."%}
{% include comandos.html content="ls, cat, sort, uniq" %}
{% include callout.html content="Primero uso **cat** para imprimir las lineas del archivo, esa salida la llevo a traves de una tuberia ( **|** ) al comando **sort**, el cual ordena las lineas de texto de forma alfabética. Esa salida la paso por **uniq -u** que solo imprime las líneas que no se repiten." type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit8@bandit.labs.overthewire.org -p 2220<br/>
bandit8@bandit:~$ ls<br/>
data.txt<br/>
bandit8@bandit:~$ cat data.txt | sort | uniq -u<br/>
UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR<br/>
</div>
{% include solucion.html content="UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR" %}

## **Nivel 9 → Nivel 10**
{% include objetivo.html content="La contraseña esta alojada en un archivo llamado **data.txt** en una de las líneas legibles por humanos, precedida de varios '**=**'"%}
{% include comandos.html content="strings, grep" %}
{% include callout.html content="Con el comando **strings** podemos extraer todas las líneas legibles por humanos y con el comando **grep** le pedimos que solo nos muestre las que tienen varios **=**" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit9@bandit.labs.overthewire.org -p 2220<br/>
bandit9@bandit:~$ strings data.txt | grep '======'
========== the*2i"4<br/>
========== password<br/>
Z)========== is<br/>
&========== truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk<br/>
</div>
{% include solucion.html content="truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk" %}

## **Nivel 10 → Nivel 11**
{% include objetivo.html content="La contraseña esta alojada en un archivo llamado **data.txt** que contiene información condificada en base64"%}
{% include comandos.html content="base64" %}
{% include callout.html content="Para decodificar base64 basta con usar el comando **base64 -d [archivo]**." type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit10@bandit.labs.overthewire.org -p 2220<br/>
bandit10@bandit:~$ base64 -d data.txt<br/>
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR<br/>
</div>
{% include solucion.html content="IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR" %}

## **Nivel 11 → Nivel 12**
{% include objetivo.html content="La contraseña para el siguiente nivel esta alojada en el archivo **data.txt**, tanto las minúsculas como las mayúsculas han sido rotadas 13 posiciones."%}
{% include comandos.html content="cat, tr" %}
{% include callout.html content="Claramente el enunciado hace renferencia al algoritmo ROT13 dónde cada letra del abecedario toma el valor de la 13º letra desde su posición. Por ejemplo, si tomamos la letra A y la rotamos 13 posiciones veriamos que nos da un valor de N. Sabiendo esto solo necesitamos un comando que nos cambie las A por N, B por O, C por P, etc. Esto lo podemos conseguir con el comando **tr** de la siguiente forma:<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **echo** [texto] | **tr** [a-zA-Z] [n-za-mN-ZA-M]<br/>
<br/>**[a-zA-Z]** **→** Le indica que queremos usar todos los carácteres que se encuentran entre la **A** y la **Z**.<br/><br/>
**[n-za-mN-ZA-M]** **→** Le indica que debe empezar como si el abecedario comenzara por **n** y terminara en **m**.<br/>
" type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit11@bandit.labs.overthewire.org -p 2220<br/>
bandit11@bandit:~$ cat data.txt <br/>
Gur cnffjbeq vf 5Gr8L4qetPEsPk8htqjhRK8XSP6x2RHh<br/>
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]<br/>
The password is 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu<br/>
</div>
{% include solucion.html content="5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu" %}

## **Nivel 12 → Nivel 13**
{% include objetivo.html content="La contraseña para el siguiente nivel esta alojada en el archivo **data.txt**, este archivo es un registro hexadecimal comprimido varias veces."%}
{% include comandos.html content="mkdir, cp, cat, xxd, file, gzip, bzip2, tar." %}
{% include callout.html content="Primero creo una carpeta temporal y copio el archivo. Cambio al directorio que antes cree y para pasar del registro hexadecimal al archivo original uso el comando **xxd -r** y vuelco el nuevo contenido en un archivo llamado **data**. Con el comando **file** compruebo el tipo de archivo.<br/><br/>
Podemos ver que es un archivo comprimido con gzip, para descomprimirlo primero le cambiamos la extensión a gz y luego usamos el comando **gzip -d**<br/><br/>Volvemos a repetir el procedimiento con **file** y vemos que ahora tenemos un archivo **bzip2**. Continuar descomprimiendo hasta tener un archivo de texto plano." type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit12@bandit.labs.overthewire.org -p 2220<br/>
#Creo el directorio, copio el archivo y me muevo al directorio creado.<br/>
bandit12@bandit:~$ mkdir /tmp/meizoso<br/>
bandit12@bandit:~$ cp data.txt /tmp/meizoso<br/>
bandit12@bandit:~$ cd /tmp/meizoso<br/>
<br/>#Con cat leo el archivo y se lo paso al comando xxd el cual volcara ĺa salida al archivo data<br/>
bandit12@bandit:/tmp/meizoso$ cat "data.txt" | xxd -r > data<br/>
<br/>#Compruebo el tipo de archivo<br/>
bandit12@bandit:/tmp/meizoso$ file data<br/>
data: gzip compressed data, was "data2.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix<br/>
<br/>#Cambio la extensión a .gz<br/>
bandit12@bandit:/tmp/meizoso$ mv data data.gz<br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data.gz  data.txt<br/>
<br/>#Descomprimo el archivo con gzip<br/>
bandit12@bandit:/tmp/meizoso$ gzip -d data.gz<br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data  data.txt<br/>
<br/>#Descomprimo el archivo con bzip2<br/>
bandit12@bandit:/tmp/meizoso$ file data<br/>
data: bzip2 compressed data, block size = 900k<br/>
bandit12@bandit:/tmp/meizoso$ mv data data.bz<br/>
bandit12@bandit:/tmp/meizoso$ bzip2 -d data.bz<br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data  data.txt<br/>
<br/>#Descomprimo el archivo con gzip<br/>
bandit12@bandit:/tmp/meizoso$ file data<br/>
data: gzip compressed data, was "data4.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix<br/>
bandit12@bandit:/tmp/meizoso$ mv data data.gz<br/>
bandit12@bandit:/tmp/meizoso$ gzip -d data.gz <br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data  data.txt<br/>
<br/>#Descomprimo el archivo con tar<br/>
bandit12@bandit:/tmp/meizoso$ file data<br/>
data: POSIX tar archive (GNU)<br/>
bandit12@bandit:/tmp/meizoso$ mv data data.tar<br/>
bandit12@bandit:/tmp/meizoso$ tar -xf data.tar<br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data5.bin  data.tar  data.txt<br/>
<br/>#Descomprimo el archivo con tar<br/>
bandit12@bandit:/tmp/meizoso$ file data5.bin<br/>
data5.bin: POSIX tar archive (GNU)<br/>
bandit12@bandit:/tmp/meizoso$ mv data5.bin data5.tar<br/>
bandit12@bandit:/tmp/meizoso$ tar -xf data5.tar<br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data5.tar  data6.bin  data.tar  data.txt<br/>
<br/>#Descomprimo el archivo con bzip2<br/>
bandit12@bandit:/tmp/meizoso$ file data6.bin <br/>
data6.bin: bzip2 compressed data, block size = 900k<br/>
bandit12@bandit:/tmp/meizoso$ mv data6.bin data6.bz<br/>
bandit12@bandit:/tmp/meizoso$ bzip2 -d data6.bz<br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data5.tar  data6  data.tar  data.txt<br/>
<br/>#Descomprimo el archivo con tar<br/>
bandit12@bandit:/tmp/meizoso$ file data6<br/>
data6: POSIX tar archive (GNU)<br/>
bandit12@bandit:/tmp/meizoso$ mv data6 data6.tar<br/>
bandit12@bandit:/tmp/meizoso$ tar -xf data6.tar<br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data5.tar  data6.tar  data8.bin  data.tar  data.txt<br/>
<br/>#Descomprimo el archivo con gzip<br/>
bandit12@bandit:/tmp/meizoso$ file data8.bin <br/>
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu May  7 18:14:30 2020, max compression, from Unix<br/>
bandit12@bandit:/tmp/meizoso$ mv data8.bin data8.gz<br/>
bandit12@bandit:/tmp/meizoso$ gzip -d data8.gz<br/>
bandit12@bandit:/tmp/meizoso$ ls<br/>
data5.tar  data6.tar  data8  data.tar  data.txt<br/>
<br/>#Leo el archivo en texto plano<br/>
bandit12@bandit:/tmp/meizoso$ file data8<br/>
data8: ASCII text<br/>
bandit12@bandit:/tmp/meizoso$ cat data8<br/>
The password is 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL<br/>
</div>
{% include solucion.html content="8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL" %}

## **Nivel 13 → Nivel 14**
{% include objetivo.html content="La contraseña para el siguiente nivel esta alojada en **/etc/bandit_pass/bandit14** y solo puede ser leido por el usuario **bandit14**. En este nivel no se obtiene una contraseña si no una **llave ssh** que puede ser usada para logearse en el siguiente nivel. <br/><br/>**NOTA:** **localhost** es el hostname de la maquina en la que estamos trabajando. "%}
{% include comandos.html content="ssh, cat" %}
{% include callout.html content="Este es un nivel muy sencillo, basta con conectarnos desde bandit13 a bandit14 con la llave ssh que encontramos en el home de bandit13. Una vez logeados como bandit14 leemos la ruta que nos indican." type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit13@bandit.labs.overthewire.org -p 2220<br/>
bandit13@bandit:~$ ls<br/>
sshkey.private<br/>
bandit13@bandit:~$ ssh bandit14@localhost -i sshkey.private<br/>
bandit14@bandit:~$ cat /etc/bandit_pass/bandit14<br/>
4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e<br/>
</div>
{% include solucion.html content="4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e" %}

## **Nivel 14 → Nivel 15**
{% include objetivo.html content="Para ver la contraseña del próximo nivel es necesario enviar la contraseña del nivel actual al localhost por el puerto 30000."%}
{% include comandos.html content="echo, nc" %}
{% include callout.html content="Para enviar la contraseña lo que haré es un **echo** con la contraseña concatenado con **nc** el cual hará el envio y el servidor nos contestará con la nueva contraseña." type="primary" %}
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh bandit14@bandit.labs.overthewire.org -p 2220<br/>
bandit14@bandit:~$ echo '4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e' | nc<br/>localhost 30000<br/>
Correct!<br/>
BfMYroe26WYalil77FoDi9qh59eK5xNr<br/>
</div>
{% include solucion.html content="BfMYroe26WYalil77FoDi9qh59eK5xNr" %}
