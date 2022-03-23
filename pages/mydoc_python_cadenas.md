---
title: Cadenas de carácteres
tags: [programacion, python]
keywords: programación, python, cadenas
summary: "Cadenas en python"
sidebar: mydoc_sidebar
permalink: mydoc_python_cadenas.html
folder: mydoc
topnav: topnav
---

{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. Carácteres especiales

| Carácteres | Significado
|-------|--------
| <center>'''texto'''</center> | Texto que puede ocupar varias líneas.
| <center>\"</center> | Escribir comillas dobles dentro de una cadena.
| <center>\'</center> | Escribir comillas simples dentro de una cadena.
| <center>\n</center> | Salto de línea.
| <center>\t</center> | Tabulador.
| <center>\</center> | Partir cadena en varias líneas.

## 2. Cadenas f

Se usan para imprimir variables dentro de cadenas de texto.
```python
nombre = "Pepe"
edad = 25
print(f"Me llamo {nombre} y tengo {edad} años.")
Me llamo Pepe y tengo 25 años.
````

**➥ Si se quieren imprimir los carácteres { } se deben escribir duplicados.**

## 3. Cadenas en bruto (raw)
Si añadimos una **r** antes de las comillas la cadena se imprimirá tal y como este escrita, sin interpretar los carácteres especiales.
```python
nombre = "Pepe"
edad = 25
print(r"Me llamo {nombre} y tengo {edad} años.")
Me llamo {nombre} y tengo {edad} años.
````

## 4. Concatenar cadenas y variables
Para concatenar cadenas usamos el carácter **'+'**.
```python
frase1 = "Me llamo Pepe"
frase2 = "tengo 25 años."
print(frase1+" y "+frase2)
Me llamo Pepe y tengo 25 años.
````

## 5. Imprimir carácteres de una string
Podemos imprimir carácteres de una string señalando la posición con [ ]

```python
string = "Me llamo Pepe"
print(string[4])
l
````

Para empezar a contar desde el final de la cadena podemos añadir **'-'** delante del índice:
```python
string = "Me llamo Pepe"
print(string[-2])
p
````
Para imprimir un grupo de carácteres usaremos **':'**
```python
string = "Me llamo Pepe"
print(string[3:8])
llamo
````
Para imprimir un grupo de carácteres desde el principio hasta una posición usaremos **':X'**
```python
string = "Me llamo Pepe"
print(string[:8])
Me llamo
````
Para imprimir un grupo de carácteres desde una posición hasta el final usaremos **'X:'**
```python
string = "Me llamo Pepe"
print(string[8:])
 Pepe
````
## 6. Longitud de una cadena
Para saber la longitud de una cadena podemos usar la función **len()**
```python
string = "Me llamo Pepe"
print(len(string))
13
````