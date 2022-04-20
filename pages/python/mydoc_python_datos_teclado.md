---
title: Ingresar datos por teclado
tags: [programacion, python]
keywords: programación, python, teclado
summary: "Como ingresar datos por teclado en python"
sidebar: mydoc_sidebar
permalink: mydoc_python_datos_teclado.html
folder: mydoc
topnav: topnav
---

{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. Como ingresar datos por teclado
### Código
```python
nombre = input("Escriba su nombre: ")
print("Buenos dias "+nombre)
````
### Ejecución
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
$python prueba_teclado.py <br/>
Escriba su nombre: Pepe<br/>
Buenos días Pepe<br/>
</div>

## 2. Conversión de tipos
{% include callout.html content="Todos los datos adquiridos por el metodo input son guardados como strings." type="primary"%}

### Pasar string a int
```python
edad = input("Escriba su edad: ")
edad = int(edad)
````

### Pasar string a float
{% include callout.html content="Los número flotantes deben ser escritos con punto no con coma" type="primary"%}
```python
peso = input("Escriba su peso: ")
peso = float(peso)
````

## 3. Variables como argumento de la función input
```python
nombre = input("Escriba su nombre: ")
apellido = input(f"Escriba su apellido, {nombre}: ")
print(f"Buenos días, {nombre} {apellido}.")
````