---
title: Script para detectar sistema operativo (TTL)
tags: [script, ttl]
keywords: script, ttl, so
summary: "Script para descubrir el sistema operativo de una máquina según su ttl"
sidebar: mydoc_sidebar
permalink: mydoc_script_os.html
folder: mydoc
topnav: topnav
---
## 1. Código

```shell
#!/bin/bash
var=$(ping $1 -c 1 | grep "ttl" | awk '{print $6}' | cut -d '=' -f 2)
if [ $var -lt 65 ];then
   echo 'Linux'
elif [ $var -gt 64 ] && [ $var -lt 129 ];then
   echo 'Windows'
elif [ $var -gt 128 ];then
   echo 'Desconocido'
else
   echo 'Error'
fi
````

## 2. Explicación

### var=$(ping $1 -c 1 | grep "ttl" | awk '{print $6}' | cut -d '=' -f 

| Parámetros | Significado
|-------|--------
| <center><b>ping $1 -c 1</b></center> | Hacemos un ping a la ip del host.
| <center><b>-grep "ttl"</b></center> | Filtramos el resultado con **grep** para mostrar solo la línea que nos interesa.
| <center><b>awk '{print $6}'</b></center> | Extraemos el sexto argumento (que corresponde a **ttl=xx**).
| <center><b>cut -d '=' -f</b></center> | Extraemos lo que hay después del **=**.

### Resto de script
{% include callout.html content="El resto del script simplemete comprueba si el número de **TTL** es menor de 65 o mayor de 64 y menor de 129 o mayor de 128.<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Menor de 65** → Linux<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Mayor de 64 y menor de 129** → Windows<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**Mayor de 129** → Desconocido (pueden ser varios SO)<br/>" type="primary" %}

