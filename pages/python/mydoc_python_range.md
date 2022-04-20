---
title: Range
tags: [programacion, python]
keywords: programación, python, range
summary: "Función range en Python"
sidebar: mydoc_sidebar
permalink: mydoc_python_range.html
folder: mydoc
topnav: topnav
---

{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. ¿Qué hace Range?
**Range** nos permite crear una lista inmutable de número enteros en sucesión aritmética.

## 2. Ejemplos
### Crear lista
```python
lista = range(10)
print(lista)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal"><pre id="terminal-pre">
>$ python range.py
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]</pre></div>

### Bucle for
```python
for x in range(0, 10):
    print('numero = ',x)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal"><pre id="terminal-pre">
>$ python range.py
numero =  0
numero =  1
numero =  2
numero =  3
numero =  4
numero =  5
numero =  6
numero =  7
numero =  8
numero =  9</pre></div>

### Cambiar operación que se realiza
Si añadirmos un tercer parámetro a range podemos definir cuantos saltos queremos dar entre números.
```python
for x in range(0, 10, 2):
    #Imprimirá los números del 0 al 9 saltando de 2 en 2
    print('numero = ',x)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal"><pre id="terminal-pre">
>$ python range.py
numero =  0
numero =  2
numero =  4
numero =  6
numero =  8</pre></div>
