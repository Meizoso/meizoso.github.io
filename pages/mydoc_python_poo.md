---
title: Programación orientada a objetos python
tags: [programacion, python]
keywords: programación, python, clases, poo, objetos
summary: "Programación orientada a objetos python"
sidebar: mydoc_sidebar
permalink: mydoc_python_poo.html
folder: mydoc
topnav: topnav
---


{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. Crear una clase
```python
class Coche():
    <code>
````
## 2. Estado inicial de un objeto
{% include callout.html content="El método especial **_\_init__()** le da unas propiedades iniciales al objeto." type="primary" %}
```python
class Coche:
    def __init__(self, ruedas, puertas):
        self.ruedas = ruedas
        self.puertas = puertas
        print("Creamos el coche con {} ruedas y {} puertas.".format(self.ruedas, self.puertas))

objeto = Coche(4, 5)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python clases.py<br/>
Creamos el coche con 4 ruedas y 5 puertas.<br/></div>
<br/>

## 3. Definir métodos
{% include callout.html content="Las funciones que van dentro de una clase se denominan **'métodos'**." type="primary" %}
```python
class Coche:
    def __init__(self, ruedas, puertas):
        self.ruedas = ruedas
        self.puertas = puertas
        print("Creamos el coche con {} ruedas y {} puertas.".format(self.ruedas, self.puertas))

    def color(self,color):
        self.color = color
        print("Pintamos el cohe de color {}.".format(self.color))

    def resumenPedido(self):
        print("Creamos un coche con {} ruedas, {} puertas y de color {}.".format(self.ruedas, self.puertas, self.color))

````

## 4. Crear instancia de la clase
{% include callout.html content="Para instanciar la clase solo necesitamos crear una variable que contenga la clase. Ejemplo: **var = clase()**. Para llamar a los métodos lo haremos con el nombre del objeto creado, un punto y el nombre del método. Ejemplo: **objeto.metodo()**" type="primary" %}
```python
class Coche:
    def __init__(self, ruedas, puertas):
        self.ruedas = ruedas
        self.puertas = puertas
        print("Creamos el coche con {} ruedas y {} puertas.".format(self.ruedas, self.puertas))

    def color(self,color):
        self.color = color
        print("Pintamos el cohe de color {}.".format(self.color))

    def resumenPedido(self):
        print("Creamos un coche con {} ruedas, {} puertas y de color {}.".format(self.ruedas, self.puertas, self.color))

objeto = Coche(4, 5)
objeto.color("Rojo")
objeto.resumenPedido()
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python clases.py<br/>
Creamos el coche con 4 ruedas y 5 puertas.<br/>
Pintamos el cohe de color Rojo.<br/>
Creamos un coche con 4 ruedas, 5 puertas y de color Rojo.<br/></div>
<br/>

## 5. Herencia
{% include callout.html content="En el siguiente código podemos ver como la clase **Rectangulo** y la clase **Triangulo** heredan las propiedades de la clase **Poligono**" type="primary" %}
```python
class Poligono:
    def __init__(self, base, altura):
        self.base=base
        self.altura=altura

class Rectangulo(Poligono):
    def area(self):
        area = self.base*self.altura
        print("El área del rectángulo es:",area)

class Triangulo(Poligono):
    def area(self):
        area = (self.base*self.altura)/2
        print("El área del triángulo es:",area)

rectangulo = Rectangulo(10, 20)
triangulo = Triangulo(20, 5)

rectangulo.area()
triangulo.area()
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python clases.py<br/>
El área del rectángulo es: 200<br/>
El área del triángulo es: 50.0<br/></div>
<br/>
