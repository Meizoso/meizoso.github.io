---
title: Diccionarios en python
tags: [programacion, python]
keywords: programación, python, diccionarios
summary: "Diccionarios en python"
sidebar: mydoc_sidebar
permalink: mydoc_python_diccionarios.html
folder: mydoc
topnav: topnav
---


{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. Qué son los diccionarios
Los diccionarios son variables que nos permiten almacenar elementos identificados por una clave (key).

## 2. Como usar un diccionario
{% include callout.html content="nombre_variable = { 'key' : 'valor' }" type="primary" %}

```python
diccionario = {'nombre':'Pepe', 'edad':25, 'ciudad':'Avilés'}
print(diccionario['nombre'])
print(diccionario['edad'])
print(diccionario['ciudad'])
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python diccionario.py<br/>
Pepe<br/>
25<br/>
Avilés<br/></div>
<br/>

## 3. Recorrer un diccionario
{% include callout.html content="nombre_variable = { 'key' : 'valor' }" type="primary" %}

```python
diccionario = {'nombre':'Pepe', 'edad':25, 'ciudad':'Avilés'}
for key in diccionario:
    print (key, ':', diccionario[key])
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python recorrer_diccionario.py<br/>
nombre : Pepe<br/>
edad : 25<br/>
ciudad : Avilés<br/></div>
<br/>

## 4. Métodos de los diccionarios
### dict()
{% include callout.html content="
Recibe como parámetro una representación de un diccionario y si es factible, devuelve un diccionario de datos
" type="primary" %}
```python
diccionario = dict(nombre='Pepe', edad=30)
print(diccionario)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python dict.py<br/>
{'nombre': 'Pepe', 'edad': 30}<br/></div>
<br/>

### zip()
{% include callout.html content="
Recibe como parámetro dos elementos iterables, ya sea una cadena, una lista o una tupla. Ambos parámetros deben tener el mismo número de elementos.
" type="primary" %}
```python
diccionario = dict(zip(('nombre','edad'),['pepe','50']))
print(diccionario)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python zip.py<br/>
{'nombre': 'pepe', 'edad': '50'}<br/></div>
<br/>

### items()
{% include callout.html content="
Devuelve una lista de tuplas, cada tupla se compone de dos elementos: el primero será la clave y el segundo, su valor.
" type="primary" %}
```python
diccionario = {'nombre':'pepe', 'edad':20}
items = dic.items()
print(items)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python items.py<br/>
dict_items([('nombre', 'pepe'), ('edad', 20)])<br/></div>
<br/>

### keys()
{% include callout.html content="
Devuelve una lista de las claves de nuestro diccionario.
" type="primary" %}
```python
diccionario = {'nombre':'pepe', 'edad':20}
claves = diccionario.keys()
print(claves)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python keys.py<br/>
dict_keys(['nombre', 'edad'])<br/></div>
<br/>

### values()
{% include callout.html content="
Devuelve una lista de los valores de nuestro diccionario.
" type="primary" %}
```python
diccionario = {'nombre':'pepe', 'edad':20}
valores = diccionario.values()
print(valores)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python values.py<br/>
dict_values(['pepe', 20])<br/></div>
<br/>

### clear()
{% include callout.html content="
Elimina todos los elementos de un diccionario.
" type="primary" %}
```python
diccionario = {'nombre':'pepe', 'edad':20}
print(diccionario)
diccionario.clear()
print(diccionario)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python clear.py<br/>
{'nombre': 'pepe', 'edad': 20}<br/>
{}<br/></div>
<br/>

### copy()
{% include callout.html content="
Copia un diccionario.
" type="primary" %}
```python
diccionario = {'nombre':'pepe', 'edad':20}
diccionario2 = diccionario.copy()
print(diccionario2)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python copy.py<br/>
{'nombre': 'pepe', 'edad': 20}<br/></div>
<br/>

### fromkeys()
{% include callout.html content="Recibe un parámetro iterable (lista, tupla) y un valor, devolviendo un diccionario que contiene como claves los elementos del iterable con el valor ingresado. Si el valor no es ingresado devolverá **none** para todas las claves." type="primary" %}
```python
diccionario = dict.fromkeys(['a', 'b', 'c'],1)
print(diccionario)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python fromkeys.py<br/>
{'a': 1, 'b': 1, 'c': 1}<br/></div>
<br/>

### get()
{% include callout.html content="Recibe como parámetro una clave y devuelve el valor de esa clave." type="primary" %}
```python
diccionario = {'a':1,'b':2}
valor = diccionario.get('b')
print("El valor es: ", valor)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python get.py<br/>
El valor es: 2<br/></div>
<br/>

### pop()
{% include callout.html content="
Recibe como parámetro una clave, elimina esta y devuelve su valor. Si no lo encuentra devuelve error.
" type="primary" %}
```python
diccionario = {'a':1,'b':2}
print('El diccionario antes de pop(): ', diccionario)
valor = diccionario.pop('a')
print('El valor es: ', valor)
print('El diccionario después de pop(): ', diccionario)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python pop.py<br/>
El diccionario antes de pop():  {'a': 1, 'b': 2}<br/>
El valor es:  1<br/>
El diccionario después de pop():  {'b': 2}<br/></div>
<br/>

### setdefault()
{% include callout.html content="
Se puede usar de dos formas. En la primera como get.
" type="primary" %}
```python
diccionario = {'a':1,'b':2}
valor = diccionario.setdefault('a')
print(valor)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python setdefault.py<br/>
1<br/></div>
<br/>

{% include callout.html content="
Y en la segunda forma, nos sirve para agregar un nuevo elemento.
" type="primary" %}
```python
diccionario = {'a':1,'b':2}
valor = diccionario.setdefault('c',8)
print(diccionario)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python setdefault.py<br/>
{'a': 1, 'b': 2, 'c': 8}<br/></div>
<br/>

### update()
{% include callout.html content="
Recibe como parámetro otro diccionario. Si tienen claves iguales, actualiza el varlor de la clave repetida; si no hay claves iguales, este par clave-valor es agregado al diccionario.
" type="primary" %}
```python
diccionario = {'a':1,'b':2}
diccionario2 = {'a':1,'b':4, 'c':7}
diccionario.update(diccionario2)
print(diccionario)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python update.py<br/>
{'a': 1, 'b': 4, 'c': 7}<br/></div>
<br/>