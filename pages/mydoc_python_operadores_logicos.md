---
title: Operadores lógicos
tags: [programacion, python]
keywords: programación, python, operadores, logicos
summary: "Operadores lógicos de python"
sidebar: mydoc_sidebar
permalink: mydoc_python_operadores_logicos.html
folder: mydoc
topnav: topnav
---


{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## Tabla de operadores lógicos

| Operador | Significado
|-------|--------
| <center><b>and</b></center> | Evalúa si el valor del lado izquierdo <b>y</b> el lado derecho se cumple.
| <center><b>or</b></center> | Evalúa si el valor del lado izquierdo <b>o</b> el lado derecho se cumple.
| <center><b>not</b></center> | Devuelve el valor opuesto al valor booleano.

## Ejemplos
### AND
```python
numero1 = 10
numero2 = 20
numero1 == 10 and numero2 == 3
False
numero1 == 10 and numero2 != 3
True
````

### OR
```python
numero1 = 10
numero2 = 20
numero1 == 10 or numero2 == 3
True
numero1 == 2 or numero2 != 3
True
numero1 < 2 or numero2 != 20
False
````

### NOT
```python
numero1 = 10
numero2 = 20
not numero1 == 10
False
not numero2 > 30
True
````