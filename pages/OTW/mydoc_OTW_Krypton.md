---
title: OverTheWire - Krypton
tags: [laboratorio, overthewire]
keywords: laboratorio, overthewire
summary: "Cómo resolver el laboratorio Bandit de OVerTheWire"
sidebar: mydoc_sidebar
permalink: mydoc_otw_krypton.html
folder: mydoc
topnav: topnav
---

## **Nivel 0 → Nivel 1**
<!--OBJETIVO-->
{% include objetivo.html content="La siguiente cadena de texto es la contraseña del próximo nivel, esta encriptada en base64: **S1JZUFRPTklTR1JFQVQ=**" %}
<!--COMANDOS-->
{% include comandos.html content="echo, base64" %}
<!--EXPLICACION-->
{% include callout.html content="Paso la cadena de texto con un **echo** al comando **base64 -d** para desencriptarlo." type="primary" %}
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">echo 'S1JZUFRPTklTR1JFQVQ=' | base64 -d<br/>
KRYPTONISGREAT<br/>
</div>
{% include solucion.html content="KRYPTONISGREAT" %}

## **Nivel 1 → Nivel 2**
<!--OBJETIVO-->
{% include objetivo.html content="La contraseña para el nivel 2 esta en la carpeta krypton2. La contraseña esta encritada con un simple sistema de rotación. Cuando se utilizan caracteres alfabéticos para texto cifrado, es normal agrupar las letras en grupos de 5 letras, independientemente de los límites de las palabras. Esto ayuda a ofuscar cualquier patrón. Este archivo ha mantenido los límites de las palabras del texto sin formato y los ha llevado al texto cifrado." %}
<!--COMANDOS-->
{% include comandos.html content="cat, tr" %}
<!--EXPLICACION-->
{% include callout.html content="Claramente en el enunciado ('simple sistema de rotación') hace renferencia al algoritmo ROT13 dónde cada letra del abecedario toma el valor de la 13º letra desde su posición. Por ejemplo, si tomamos la letra A y la rotamos 13 posiciones veriamos que nos da un valor de N. Sabiendo esto solo necesitamos un comando que nos cambie las A por N, B por O, C por P, etc. Esto lo podemos conseguir con el comando **tr** de la siguiente forma:<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **cat** [archivo] | **tr** [a-zA-Z] [n-za-mN-ZA-M]<br/>
<br/>**[a-zA-Z]** **→** Le indica que queremos usar todos los carácteres que se encuentran entre la **A** y la **Z**.<br/><br/>
**[n-za-mN-ZA-M]** **→** Le indica que debe empezar como si el abecedario comenzara por **n** y terminara en **m**.<br/>" type="primary" %}
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">ssh krypton1@krypton.labs.overthewire.org -p 2231<br/>
krypton1@krypton:~$ cd /krypton/krypton1<br/>
krypton1@krypton:/krypton/krypton1$ cat README<br/>
krypton1@krypton:/krypton/krypton1$ cat krypton2<br/>
YRIRY GJB CNFFJBEQ EBGGRA<br/>
krypton1@krypton:/krypton/krypton1$ cat krypton2 | tr [A-Za-z] [N-ZA-Mn-za-m]<br/>
LEVEL TWO PASSWORD ROTTEN<br/>
</div>
{% include solucion.html content="ROTTEN" %}