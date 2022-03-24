---
title: Nmap
tags: [software, nmap]
keywords: software, nmap
summary: "Como usar Nmap."
sidebar: mydoc_sidebar
permalink: mydoc_reco_nmap.html
folder: mydoc
topnav: topnav
---

## 1. Escaneo ICMP sin resolución de nombres
{% include callout.html content="**-sP** → Ecaneno ICMP.<br/>**-n** → Sin resolución de nombres." type="primary" %}
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ nmap -sP -n 192.168.1.0/24<br/>
Starting Nmap 7.92 ( https://nmap.org ) at 2022-03-15 16:39 CET<br/>
Nmap scan report for 192.168.1.1<br/>
Host is up (0.0026s latency).<br/>
Nmap scan report for 192.168.1.11<br/>
Host is up (0.0064s latency).<br/>
Nmap scan report for 192.168.1.30<br/>
Host is up (0.021s latency).<br/>
Nmap scan report for 192.168.1.62<br/>
Host is up (0.0042s latency).<br/>
Nmap scan report for 192.168.1.70<br/>
Host is up (0.068s latency).<br/>
Nmap done: 256 IP addresses (5 hosts up) scanned in 3.52 seconds<br/></div>
<br/>

## 2. Escaneo de todos los puertos y la versión de todos los servicios
{% include callout.html content="**-p-** → Ecanenar todos los puertos.<br/>**-sV** → Vaersión de los servicios." type="primary" %}
{% include warning.html content="Este tipo de escaneo es muy ruidoso y lento por lo que no se recomienda hacerlo."%}
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ nmap -p- -sV 192.168.1.30<br/>
Starting Nmap 7.92 ( https://nmap.org ) at 2022-03-15 16:39 CET<br/>
Nmap scan report for DESKTOP-1NG1D24.home (192.168.1.30)<br/>
Host is up (0.095s latency).<br/>
All 65535 scanned ports on DESKTOP-1NG1D24.home (192.168.1.30) are in ignored states.<br/>
Not shown: 65535 closed tcp ports (conn-refused)<br/>

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .<br/>
Nmap done: 1 IP address (1 host up) scanned in 32.36 seconds<br/></div>
<br/>

## 2. Escaneo de toda la red
{% include callout.html content="Para escanear toda la red debemos cambiar el número de host por *." type="primary" %}
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ nmap 192.168.1.*<br/>
Starting Nmap 7.92 ( https://nmap.org ) at 2022-03-17 08:44 CET<br/>
Nmap scan report for liveboxfibra (192.168.1.1)<br/>
Host is up (0.028s latency).<br/>
Not shown: 993 closed tcp ports (conn-refused)<br/>
PORT     STATE    SERVICE<br/>
53/tcp   open     domain<br/>
80/tcp   open     http<br/>
139/tcp  open     netbios-ssn<br/>
443/tcp  open     https<br/>
445/tcp  open     microsoft-ds<br/>
6969/tcp open     acmsoda<br/>
8080/tcp filtered http-proxy<br/><br/>

Nmap scan report for linux.home (192.168.1.30)<br/>
Host is up (0.033s latency).<br/>
All 1000 scanned ports on linux.home (192.168.1.30) are in ignored states.<br/>
Not shown: 1000 closed tcp ports (conn-refused)<br/><br/>

Nmap scan report for Archer_C1200.home (192.168.1.62)<br/>
Host is up (0.00082s latency).<br/>
Not shown: 996 closed tcp ports (conn-refused)<br/>
PORT      STATE SERVICE<br/>
22/tcp    open  ssh<br/>
80/tcp    open  http<br/>
1900/tcp  open  upnp<br/>
20005/tcp open  btx<br/><br/>

Nmap done: 256 IP addresses (3 hosts up) scanned in 40.61 seconds<br/></div>
<br/>

## 3. Excluir una IP del escaneo
{% include callout.html content="nmap 192.168.1.* --exclude 192.168.1.30" type="primary" %}
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ nmap 192.168.1.* --exclude 192.168.1.30<br/>
Starting Nmap 7.92 ( https://nmap.org ) at 2022-03-17 09:02 CET<br/>
Nmap scan report for liveboxfibra (192.168.1.1)<br/>
Host is up (0.031s latency).<br/>
Not shown: 993 closed tcp ports (conn-refused)<br/>
PORT     STATE    SERVICE<br/>
53/tcp   open     domain<br/>
80/tcp   open     http<br/>
139/tcp  open     netbios-ssn<br/>
443/tcp  open     https<br/>
445/tcp  open     microsoft-ds<br/>
6969/tcp open     acmsoda<br/>
8080/tcp filtered http-proxy<br/>
<br/>
Nmap scan report for 192.168.1.11<br/>
Host is up (0.036s latency).<br/>
All 1000 scanned ports on 192.168.1.11 are in ignored states.<br/>
Not shown: 1000 closed tcp ports (conn-refused)<br/>
<br/>
Nmap scan report for 192.168.1.62<br/>
Host is up (0.00093s latency).<br/>
Not shown: 996 closed tcp ports (conn-refused)<br/>
PORT      STATE SERVICE<br/>
22/tcp    open  ssh<br/>
80/tcp    open  http<br/>
1900/tcp  open  upnp<br/>
20005/tcp open  btx<br/>
<br/>
Nmap done: 255 IP addresses (3 hosts up) scanned in 41.44 seconds<br/></div>
<br/>

## 4. Escaneo TCP SYN

Este comando comprueba si el puerto objetivo está escuchando. Mediante este comando se puede llevar a cabo una técnica conocida como escaneo **half-opening**, esta comienza como una conexión normal pero no llega a establecerse un handshake por ambas partes, sino que enviamos un único paquete SYN y esperamos la respuesta.

{% include callout.html content="nmap -sS [IP]" type="primary" %}

<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ nmap -sS 127.0.0.1 <br/>
Starting Nmap 7.92 ( https://nmap.org ) at 2022-03-25 00:04 CET<br/>
Nmap scan report for localhost (127.0.0.1)<br/>
Host is up (0.024s latency).<br/>
Not shown: 998 closed tcp ports (reset)<br/>
PORT     STATE SERVICE<br/>
4000/tcp open  remoteanything<br/>
8888/tcp open  sun-answerbook<br/><br/>

Nmap done: 1 IP address (1 host up) scanned in 1.16 seconds<br/></div>
<br/>

## Resumen de los escaneos de NMAP

| Comando | Explicación |
|--------|--------|
| <b>nmap -sP -n [IP]/24</b> | Escaneo ICMP sin resolución de nombres |
| <b>nmap -p- -sV [IP]</b> | Escaneo de todos los puertos y la versión de todos los servicios |
| <b>nmap 192.168.0.*</b> | Escaneo de toda la red |
| <b>nmap -sS [IP]</b> | Escaneo TCP SYN (half-opening)|
