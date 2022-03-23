---
title: Funciones en python
tags: [programacion, python]
keywords: programación, python, funciones
summary: "Funciones en python"
sidebar: mydoc_sidebar
permalink: mydoc_python_funciones.html
folder: mydoc
topnav: topnav
---


{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. Declarar y llamar a la función
```python
def myFuncion():
    print("Esto es una función")
myFuncion()
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python pruebas.py<br/>
Esto es una función<br/></div>
<br/>

## 2. Retorno de valores
```python
def myFuncion():
    suma = 2 + 3
    return suma
print(myFuncion())
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python retorno.py<br/>
5<br/></div>
<br/>

## 3. Retorno de múltiples valores
```python
def myFuncion():
    suma = 2 + 3
    resta = 4 - 1
    nombre = 'Pepe'
    return suma, resta, nombre
print(myFuncion())
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python retorno_multiple.py<br/>
(5, 3, 'Pepe')<br/></div>
<br/>

## 4. Envio de valores
```python
def myFuncion(n1, n2):
    suma = n1 + n2
    return suma
print(myFuncion(2, 8))
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python envio_valores.py<br/>
10<br/></div>
<br/>

## 5. Enviar los argumentos por nombre
```python
def myFuncion(n1, n2):
    suma = n1 + n2
    return suma
print(myFuncion(n2=2, n1=8))
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python envio_valores.py<br/>
10<br/></div>
<br/>

## 6. Valores por defecto de los argumentos
```python
def myFuncion(n1=None, n2=None):
    print(n1)
    print(n2)
myFuncion()
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python envio_valores.py<br/>
None<br/>
None<br/></div>
<br/>

## 6. Argumentos indeterminados
{% include callout.html content="Los parámetros indeterminados por posición y por nombre sirven cuando no sabemos el número de parámetros que le pasaremos a la función." type="primary" %}

### Por posición
{% include callout.html content="Para recibir un número indeterminado de parámetros por posición, debemos crear una lista dinámica de elementos definiendo el parámetro con un asterisco." type="primary" %}
```python
def miFuncion(*argumentos):
    for arg in argumentos:
        print(arg)
miFuncion('hola', 3, 25, ['adios', 8])
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python por_posicion.py<br/>
hola<br/>
3<br/>
25<br/>
['adios', 8]<br/></div>
<br/>

### Por nombre
{% include callout.html content="Para recibir un número indeterminado de parámetros por nombre (clave-valor), debemos crear un diccionario de argumentos definiendo el parámetro con dos asteriscos" type="primary" %}
```python
def miFuncion(**argumentos):
    print(argumentos)
miFuncion(a=1, b='hola', c=23)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python por_nombre.py<br/>
{'a': 1, 'b': 'hola', 'c': 23}<br/></div>
<br/>

### Por posición y por nombre
{% include callout.html content="Si queremos aceptar ambos tipos de parámetros simultáneamente, entonces debemos crear ambas colecciones dinámicas. Primero los argumentos indeterminados por valor y luego los que son por clave y valor." type="primary" %}
```python
def miFuncion(*posicion, **nombre):
    print('Por posicion:')
    for arg_p in posicion:
        print(arg_p)

    print('Por nombre:')
    for arg_n in nombre:
        print(arg_n,'=' ,nombre[arg_n])

miFuncion(1, 2, 3, nombre='Pepe', Edad=25)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python por_posicion.py<br/>
Por posicion:<br/>
1<br/>
2<br/>
3<br/>
Por nombre:<br/>
nombre = Pepe<br/>
Edad = 25<br/></div>
<br/>

## 7. Funciones recursivas
{% include callout.html content="Son funciones que se llaman a si mismas durante su propia ejecución." type="primary" %}
```python
def cuentaAtras(numero):
    numero -= 1
    if numero > 0:
        print (numero)
        cuentaAtras(numero)
    else:
        print("Fin de la cuenta atras")

cuentaAtras(5)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python f_recursivas.py<br/>
4<br/>
3<br/>
2<br/>
1<br/>
Fin de la cuenta atras<br/></div>
<br/>

## 8. Funciones integradas
{% include callout.html content="El interprete Python tiene un número de funciones integradas (built-in) dentro del módulo __builtins__" type="primary" %}
### Lista de funciones integradas

|Funciones Built-in|
------- | ------- | ------- | ------- | ------- |
abs() |delattr() | hash() | memoryview() | set() |
all() | dict() | help() | min() | setattr() |
any() | dir() | hex() | next() | slice() |
ascii() | divmod() | id() | object() | sorted() |
bin() | enumerate() | input() | oct() | staticmethod() |
bool() | eval() | int() | open() | str() |
breakpoint() | exec() | isinstance() | ord() | sum() |
bytearray() | filter() | issubclass() | pow() | super() |
bytes() | float() | iter() | print() | tuple() |
callable() | format() | len() | property() | type() |
chr() | frozenset() | list() | range() | vars() |
classmethod() | getattr() | locals() | repr() | zip() |
compile() | globals() | map() | reversed() | _\_import__() |
complex() | hasattr() | max() | round() |  |
