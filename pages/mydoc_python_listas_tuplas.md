---
title: Listas y tuplas
tags: [programacion, python]
keywords: programación, python, listas, tuplas
summary: "Listas y tuplas en python"
sidebar: mydoc_sidebar
permalink: mydoc_python_listas_tuplas.html
folder: mydoc
topnav: topnav
---

{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. Diferencia listas y tuplas
Las listas permiten ser moidificadas después de crearlas, en cambio las tuplas no pueden ser modificadas.

## 2. Como se usa una lista
### Crear lista
```python
>>> lista = ["uno", 2, "tres"]
````
### Imprimir un elemento de la lista
```python
>>> lista = ["uno", 2, "tres"]
>>> print(lista[0])
uno
````
### Imprimir un elemento de la lista indice negativo
```python
>>> lista = ["uno", 2, "tres"]
>>> print(lista[-1])
tres
````
### Imprimir conjunto de elementos de la lista
```python
>>> lista = ["uno", 2, "tres"]
>>> print(lista[0:2])
['uno', 2]
````
### Añadir un elemento a la lista (append)
```python
>>> lista = ["uno", 2, "tres"]
>>> print(lista)
['uno', 2, 'tres']
>>> lista.append(4)
>>> print(lista)
['uno', 2, 'tres', 4]
````
### Eliminar un elemento por su índice (pop)
```python
>>> print(lista)
['uno', 2, 'tres', 4]
>>> lista.pop(2)
'tres'
>>> print (lista)
['uno', 2, 4]
````
### Eliminar un elemento por su valor (remove)
```python
>>> print (lista)
['uno', 2, 4]
>>> lista.remove(4)
>>> print (lista)
['uno', 2]
````
## 3. Como se usa una tupla
### Crear tupla
```python
>>> tupla = 1, 2, "tres"
>>> print (tupla)
(1, 2, 'tres')
````
### Imprimir un elemento de la tupla
```python
>>> tupla = (1, 2, "tres")
>>> print(tupla[0])
1
````
### Imprimir un elemento de la tupla indice negativo
```python
>>> tupla = (1, 2, "tres")
>>> print(tupla[-1])
tres
````
### Imprimir conjunto de elementos de la tupla
```python
>>> tupla = (1, 2, "tres")
>>> print(tupla[0:2])
[1, 2]
````