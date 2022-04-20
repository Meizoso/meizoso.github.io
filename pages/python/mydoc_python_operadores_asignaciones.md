---
title: Operadores de asignaciones
tags: [programacion, python]
keywords: programación, python, operadores, asignaciones
summary: "Operadores de asignación de python"
sidebar: mydoc_sidebar
permalink: mydoc_python_operadores_asignaciones.html
folder: mydoc
topnav: topnav
---


{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## Tabla de operadores de asignaciones

| Operador | Significado
|-------|--------
| <center><b>=</b></center> | Asigna un valor a una variable
| <center><b>+=</b></center> | Suma a la variable del lado izquierdo el valor del lado derecho
| <center><b>-=</b></center> | Resta a la variable del lado izquierdo el valor del lado derecho
| <center><b>*=</b></center> | Multiplica a la variable del lado izquierdo el valor del lado derecho
| <center><b>/=</b></center> | Divide a la variable del lado izquierdo el valor del lado derecho
| <center><b>**=</b></center> | Calcula el exponente a la variable del lado izquierdo con el valor del lado derecho
| <center><b>//=</b></center> | Calcula la división entera de la variable del lado izquierdo con el valor del lado derecho
| <center><b>%=</b></center> | Devuelve el resto de la división de la variable del lado izquierdo con el valor del lado derecho

## Ejemplos
### Asignar valor =
```python
numero1 = 10
numero1
10
````

### Sumar variable +=
```python
numero1 = 10
numero1 += 5
numero1
15
````

### Restar variable -=
```python
numero1 = 10
numero1 -= 2
numero1
8
````

### Multiplicar variable *=
```python
numero1 = 10
numero1 *= 2
numero1
20
````

### Dividir variable /=
```python
numero1 = 10
numero1 /= 2
numero1
5.0
````

### Elevar variable **=
```python
numero1 = 10
numero1 **= 2
numero1
100
````

### División entera de variable //=
```python
numero1 = 10
numero1 //= 3
numero1
3
````

### Módulo variable %=
```python
numero1 = 10
numero1 %= 3
numero1
1
````