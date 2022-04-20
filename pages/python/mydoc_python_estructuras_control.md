---
title: Estructuras de control y bucles
tags: [programacion, python]
keywords: programación, python, estructuras, control, bucles
summary: "Estructuras de control y bucles de python"
sidebar: mydoc_sidebar
permalink: mydoc_python_estructuras_control.html
folder: mydoc
topnav: topnav
---


{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## Tabla de estructuras de control y bucles

| Operador | Significado | Uso
|-------|--------
| <center><b>if</b></center> | **Si** se cumple la expresión condicional se ejecuta el bloque de sentencias seguidas.
| <center><b>if else y elif</b></center> | **De lo contrario Si** se cumple la expresión condicional se ejecuta el bloque de sentencias seguidas.
<center><b>else</b></center> | **De lo contrario** se cumple sin evaluar ninguna expresión condicional y ejecuta el bloque de sentencias seguidas.
<center><b>is</b></center> | Se podría traducir por **==**. Comprueba si los dos valores son iguales.
<center><b>in</b></center> | Comprueba si un valor esta en una colección de valores (Listas/Tuplas)
<center><b>not in</b></center> | Comprueba si un valor **no** esta en una colección de valores (Listas/Tuplas)
| <center><b>while</b></center> | **Mientras** la condición se cumpla se seguirá ejecutando el código
| <center><b>for</b></center> | Se utiliza para recorrer los elementos de un objeto iterable (lista, tupla, conjunto, diccionario, …) y ejecutar un bloque de código

## Ejemplos
### If
```python
numero1 = 10
numero2 = 20
if numero1 == numero2:
    print("Son iguales")
````

### if else y elif
```python
numero1 = 10
numero2 = 20
if numero1 != 10:
    print("Número 1 es distinto a 10")
elif numero1 == 30:
    print("Número 1 es igual a 30")
````

### else
```python
numero1 = 10
numero2 = 20
if numero1 == numero2:
    print("Número 1 es igual a Número 2")
else:
    print("Número 1 es distinto a Número 2")
````

### is
```python
n1 = 10
n2 = 20
if n1 is n2:
    print("Son iguales")
else:
    print("Son distintos")
````

### in
```python
numero1 = (10, 20)
if 15 in numero1:
    print("Número encontrado")
else:
    print("Número no encontrado")
````

### not in
```python
numero1 = (10, 20)
if 15 not in numero1:
    print("El número no esta en la lista")
else:
    print("El número esta en la lista")
````

### while
```python
numero1 = 0
numero2 = 5
while numero1 < numero2:
    print("Tu número es: ", numero1)
    numero1 += 1
````
#### Salida while
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python while.py<br/>
Tu número es:  0<br/>
Tu número es:  1<br/>
Tu número es:  2<br/>
Tu número es:  3<br/>
Tu número es:  4<br/></div>
<br/>

### for
```python
numero1 =(0, 2, 5, 8)
for n in numero1:
    print("Tu número es: ",n
````
#### Salida for
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python for.py<br/>
Tu número es:  0<br/>
Tu número es:  2<br/>
Tu número es:  5<br/>
Tu número es:  8<br/></div>
<br/>