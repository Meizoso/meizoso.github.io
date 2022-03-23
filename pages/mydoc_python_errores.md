---
title: Errores en python
tags: [programacion, python]
keywords: programación, python, errores
summary: "Captura de errores en python"
sidebar: mydoc_sidebar
permalink: mydoc_python_errores.html
folder: mydoc
topnav: topnav
---


{% include warning.html content="Esto <b>NO</b> es una guía de aprendizaje. Esto es una guía rapida para refrescar conocimientos. Si quieres aprender python te dejo unos enlaces en la sección <b>Aprender python</b>.
 "%}

## 1. Capturar errores
### Código sin captura del error
```python
def myFuncion():
    n_id = int(input("Introduzca su número de identificación:"))
myFuncion()
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python errores.py<br/>
Introduzca su número de identificación:abc<br/>
Traceback (most recent call last):<br/>
  File "/home/meizoso/pruebas.py", line 4, in <\module><br/>
    myFuncion()<br/>
  File "/home/meizoso/pruebas.py", line 2, in myFuncion<br/>
    n_id = int(input("Introduzca su número de identificación:"))<br/>
ValueError: invalid literal for int() with base 10: 'abc'<br/></div>
<br/>


### Código con captura del error
```python
def myFuncion():
    try:
        n_id = int(input("Introduzca su número de identificación:"))
    except:
        print('ERROR: Debe introducir un número.')
myFuncion()
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python errores.py<br/>
Introduzca su número de identificación: abc<br/>
ERROR: Debe introducir un número.<br/></div>
<br/>

### Código con captura del error y finally
{% include callout.html content="El código escrito en **finally:** se ejecuta siempre, de un error o no." type="primary" %}
```python
def myFuncion():
    try:
        n_id = int(input("Introduzca su número de identificación:"))
    except:
        print('ERROR: Debe introducir un número.')
    finally:
        print ('Saliendo del programa....')
myFuncion()
````
<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python errores.py<br/>
Introduzca su número de identificación:asd<br/>
ERROR: Debe introducir un número.<br/>
Saliendo del programa....<br/><br/>
>$ python errores.py<br/>
Introduzca su número de identificación:123<br/>
Saliendo del programa....<br/></div>
<br/>

## 2. Capturar el error según su tipo
### Tabla con los tipos de errores

| Tipo de error | Explicación |
|--------|--------|
| <b>ArithmeticError</b> | Errores aritméticos en general |
| <b>FloatingPointError</b> | Error en una operación de coma flotante |
| <b>OverflowError</b> | Resultado demasiado grande para poder representarse |
| <b>ZeroDivisionError</b> | Se intenta dividir por cero |
| <b>EOFError</b> | Se intenta leer más allá del final de un fichero |
| <b>ImportError</b> | No se encuentra el módulo que se quiere importar |
| <b>IndexError</b> | El índice de la secuencia esta fuera del rango |
| <b>KeyError</b> | La clave no existe |
| <b>Name Error</b> | No se encuentran variables/funciones/otros elementos con el nombre indicado|
| <b>RuntimeError</b> | Error en un tiempo de ejecución no especificado |
| <b>SyntaxError</b> | Error interno del intérprete |
| <b>TyeError</b> | Tipo de argumento inapropiado |
| <b>ValueError</b> | Valor de arguemento inapropiado |
| <b>KeyboardInterrupt</b> | Programa interrumpido por el usuario |

### Ejmeplo de uso
```python
def myFuncion():
    try:
        n_id = int(input("Introduzca su número de identificación:"))
    except ValueError:
        print('ERROR: Debe introducir un número.')
    except KeyboardInterrupt:
        print('Programa interrumpido por el usuario')
    finally:
        print ('Saliendo del programa....')
myFuncion()
````

<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ python errores.py<br/>
Introduzca su número de identificación:asd<br/>
ERROR: Debe introducir un número.<br/>
Saliendo del programa....<br/><br/>
>$ python errores.py<br/>
Introduzca su número de identificación:^CPrograma interrumpido por el usuario<br/>
Saliendo del programa....<br/></div>
<br/>
