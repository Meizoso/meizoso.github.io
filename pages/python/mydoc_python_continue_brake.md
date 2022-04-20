---
title: Continue y brake
tags: [programacion, python]
keywords: programación, python, continue, brake
summary: "Continue y brake en Python"
sidebar: mydoc_sidebar
permalink: mydoc_python_continue_brake.html
folder: mydoc
topnav: topnav
---

{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. ¿Qué hacen Continue y Brake?
Sirven para saltar o detener un bucle.

## 2. Uso
Con **continue** salto el valor 3 y con **brake** le indico que si el valor es igual a 7 pare el bucle.
```python
for x in range(0, 10):
    if x == 3:
        continue
    if x == 7:
        break
    print(x)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal"><pre id="terminal-pre">
>$ python range.py
0
1
2
4
5
6</pre></div>

## 3. Ejemplo
### Extraer números divisibles de un número que nosostros le demos
```python
# Extraer los numeros divisibles de 5 en un range del 1 al 51:

n = 5

for x in range(1, 51):
    if x%n != 0:
        continue
    print(x)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal"><pre id="terminal-pre">
>$ python continue.py
5
10
15
20
25
30
35
40
45
50</pre></div>