---
title: Teoría sobre IPs
tags: [teoria]
keywords: teoria, ip
summary: "Teoría sobre las IPs."
sidebar: mydoc_sidebar
permalink: mydoc_teoria_IP.html
folder: mydoc
topnav: topnav
---

## 1. ¿Qué es una IP?
Una IP es un número **único** que identifica cada dispositivo que esta conectado a una red.

El formato usado es un código de cuatro números separados por puntos:

&nbsp;&nbsp;&nbsp;&nbsp;192.168.1.5

Cada número puede ir desde los 0 hasta 255:

**IP correcta:** 192.168.0.14<br/>
**IP incorrecta:** 321.168.0.14 [El primer número supera el 255]

Estos valores también se escriben de forma binaria quedándonos 4 octetos separados por puntos:

00000000.00000000.00000000.00000000

Si quisieramos representar la IP 192.168.1.5 pasaríamos cada número a bianario y los escribiriamos de la siguiente forma:

192 = 11000000<br/>
168 = 10101000<br/>
001 = 00000001<br/>
005 = 00000101<br/>

IP = 11000000.10101000.00000001.00000101

## 2. IP privada e IP pública
La dirección IP **privada** es un número único que nos identifica **dentro** de nuesta red interna.
En linux podemos verla con el comando **ifconfig**:
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ifconfig<br/>
enp34s0: flags=4163<-UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;inet <b>192.168.1.30</b>  netmask 255.255.255.0  broadcast 192.168.1.255<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;inet6 fe80::65ae:bf60:8cc2:ff83  prefixlen 64  scopeid 0x20<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ether 2c:f0:5d:27:84:e1  txqueuelen 1000  (Ethernet)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;RX packets 31718  bytes 38900576 (37.0 MiB)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;RX errors 0  dropped 0  overruns 0  frame 0<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TX packets 12469  bytes 1507266 (1.4 MiB)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0<br/>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;device interrupt 39  base 0xd000<br/></div><br/>

La dirección IP **pública** es un número único que identifica nuestra red interna con el exterior. En linux la podemos ver con **curl**
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$curl ifconfig.me<br/>
<b>90.68.45.2</b><br/></div>

<br/>
## 3. Clases de IPs
<u><b>Clase A</b></u>

El primer bit del primer octeto siempre es 0. Por lo tanto, el primer octeto varía de 000000001 a 01111111, es decir de 1 a 127. Las direcciones 127.x.x.x están reservadas para loopback por lo que diremos que la Clase A abarca desde 1 a 126.

La máscara de subred predeterminada para la clase es 255.0.0.0

Formato Clase A = 0NNNNNNN.HHHHHHHH.HHHHHHHH.HHHHHHHH

N = Network ID<br/>
H = Host
<br/><br/>

<u><b>Clase B</b></u>

La clase B tiene 10 en los dos primeros bits del primer octeto, varía de 10000000 a 10111111, es decir de 128 a 191

La máscara de subred predeterminada para la clase es 255.255.0.0

Formato Clase B = 10NNNNNN.HHHHHHHH.HHHHHHHH.HHHHHHHH

N = Network ID<br/>
H = Host
<br/><br/>

<u><b>Clase C</b></u>

El primer octeto de la clase C es 110, varía de 11000000 a 11011111, es decir de 192 a 223
La máscara de subred predeterminada para la clase es 255.255.255.0

Formato Clase C = 110NNNNNN.HHHHHHHH.HHHHHHHH.HHHHHHHH

N = Network ID<br/>
H = Host

<u><b>Clase D</b></u>

El primer octeto de la clase D es 1110, varía de 11100000 a 11101111, es decir de 224 a 239. La clase D se utilizan para identificar grupos de multidifusión de forma única.
<br/><br/>

<u><b>Clase E</b></u>

Esta clase varía de 240.0.0.0 a 255.255.255.254. Esta clase esta reservada para fines experimentales.
<br/><br/>