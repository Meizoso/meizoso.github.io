---
title: Conjuntos
tags: [programacion, python]
keywords: programación, python, conjuntos
summary: "Conjuntos en python"
sidebar: mydoc_sidebar
permalink: mydoc_python_conjuntos.html
folder: mydoc
topnav: topnav
---

{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. Diferencia entre los conjuntos y las listas
Los conjuntos guardan los datos de forma desordenada y no pueden tener elementos repetidos.

## 2. Creación de un conjunto
Para crear un conjunto se utilizan **{ }**
```python
conjunto = {2, 4, 7, 9}
````
Para crear un conjunto vacío se utiliza **set()**
```python
conjunto = set()
````

## 3. Añadir elementos: add()
```python
conjunto = {2, 5, 8}
conjunto.add(3)
print(conjunto)
````
Salida add():
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python add.py<br/>
{8, 2, 3, 5}<br/></div>
<br/>
{% include callout.html content="Si intentamos añadir un elemento que ya esta en el conjunto simplemente será ignorado." type="primary" %}

## 4. Eliminar elementos: discard()
```python
conjunto = {2, 5, 8}
conjunto.discard(5)
print(conjunto)
````
Salida discard():
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python discard.py<br/>
{8, 2}<br/></div>
<br/>
{% include callout.html content="Si intentamos eliminar un elemento que no esta en el conjunto simplemente será ignorado." type="primary" %}

## 5. Eliminar elementos: remove()
```python
conjunto = {2, 5, 8}
conjunto.remove(5)
print(conjunto)
````
Salida remove():
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python remove.py<br/>
{8, 2}<br/></div>
<br/>
{% include callout.html content="Si intentamos eliminar un elemento que no esta en el conjunto lanza una excepción **KeyError**" type="primary" %}

```python
conjunto = {2, 5, 8}
conjunto.remove(6)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python remove.py<br/>
Traceback (most recent call last):<br/>
&nbsp;&nbsp;File "/home/meizoso/pruebas.py", line 2, in < module><br/>
&nbsp;&nbsp;&nbsp;&nbsp;conjunto.remove(4)<br/>
KeyError: 4<br/></div>
<br/>

## 5. Eliminar elementos de forma aleatoria: pop()
Ya que un conjunto no esta ordenado al usar pop() se eliminará un elemento de forma aleatoria.
```python
conjunto = {2, 5, 8, 9}
conjunto.pop()
print(conjunto)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python pop.py<br/>
{9, 2, 5}<br/></div>
<br/>

## 5. Eliminar todos los elementos: clear()
**clear()** elimina todos los elementos contenidos en un conjunto.
```python
conjunto = {2, 5, 8, 9}
print("Antes de usar clear() = ",conjunto)
conjunto.clear()
print("Después de usar clear() = ",conjunto)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python clear.py<br/>
Antes de usar clear() =  {8, 9, 2, 5}<br/>
Después de usar clear() =  set()<br/></div>
<br/>

## 6. Unión de conjuntos |
Podemos unir dos conjuntos con el carácter **|**. En caso de que haya elementos repetidos solo se copiara uno de ellos.
```python
conjunto1 = {2, 5}
conjunto2 = {8, 9, 2}
conjunto3 = conjunto1 | conjunto2
print(conjunto3)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python union.py<br/>
{2, 5, 8, 9}<br/></div>
<br/>

## 7. Intersección de conjuntos &
La intersección crea un nuevo conjunto con los elementos que se repitan entre los otros dos conjuntos. 
```python
conjunto1 = {2, 5, 9}
conjunto2 = {8, 9, 2}
conjunto3 = conjunto1 & conjunto2
print(conjunto3)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python interseccion.py<br/>
{9, 2}<br/></div>
<br/>

## 8. Diferencia de conjuntos -
la diferencia crea un nuevo conjunto con los elementos del conjunto1 que no se repiten entre los otros conjuntos. 
```python
conjunto1 = {2, 5, 9}
conjunto2 = {8, 9, 2}
conjunto3 = conjunto1 - conjunto2
print(conjunto3)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python interseccion.py<br/>
{5}<br/></div>
<br/>