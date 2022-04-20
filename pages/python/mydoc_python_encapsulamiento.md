---
title: Encapsulamiento
tags: [programacion, python]
keywords: programación, python, encapsulamiento
summary: "Encampsulamiento en Python"
sidebar: mydoc_sidebar
permalink: mydoc_python_encapsulamiento.html
folder: mydoc
topnav: topnav
---

{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. ¿Qué hace el encapsulamiento?
El **encapsulamiento** hace que los atributos o métodos internos de una clase no se puedan acceder ni modificar desde fuera, sino que tan solo el propio objeto pueda acceder a ellos.

## 2. Encapsulando metódos y atributos
### Código sin encapsulamiento
```python
class Clase:
    atributo_clase = "Hola"
    def __init__(self, atributo_instancia):
        self.atributo_instancia = atributo_instancia

mi_clase = Clase("Mundo")
print(mi_clase.atributo_clase)
print(mi_clase.atributo_instancia)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal"><pre id="terminal-pre">
>$ python encapsulamiento.py
Hola
Mundo</pre></div>

<br/>

### Código con encapsulamiento
```python
class Clase:
    __atributo_clase = "Hola"
    def __init__(self, atributo_instancia):
        self.atributo_instancia = atributo_instancia

mi_clase = Clase("Mundo")
print(mi_clase.atributo_clase)
print(mi_clase.atributo_instancia)
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal"><pre id="terminal-pre">
>$ python encapsulamiento.py
Traceback (most recent call last):
  File "/home/p4vlichenko/python/range.py", line 7, in <module>
    print(mi_clase.atributo_clase)
AttributeError: 'Clase' object has no attribute 'atributo_clase'
</pre></div>