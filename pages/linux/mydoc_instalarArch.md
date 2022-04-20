---
title: Instalar Arch
tags: [linux, arch]
keywords: instalacion, arch, archlinux, sistemas, operativos, sistemas operativos
last_updated: 3 Marzo 2022
summary: "Como realizar la instalación de Arch a través de su instalador."
sidebar: mydoc_sidebar
permalink: mydoc_instalarArch.html
folder: mydoc
topnav: topnav
---

## 1 - Bootear Arch desde un pendrive
![Image text](images/InstalarArch/01.png)

## 2 - Archinstall
Usar el comando **archinstall** para comenzar la instalación.
![Image text](images/InstalarArch/02.png)

## 3 - Idioma del teclado
Elegiremos el idioma de nuestro teclado escribiendo el número que aparece al lado de las iniciales del país.
![Image text](images/InstalarArch/03.png)

## 4 - Seleccionar espejo
Seleccionar el espejo desde el que queremos realizar las descargas. Elegiremos el país más cercano, en mi caso España.
![Image text](images/InstalarArch/04.png)

## 5 - Discos
Seleccionamos el disco donde queremos hacer la instalación.
![Image text](images/InstalarArch/05.png)

## 6 - Eliminar disco
Seleccionamos que queremos eliminar el disco completo.
![Image text](images/InstalarArch/06.png)

## 7 - Sistema de ficheros
Escogemos que sistema de ficheros queremos usar.
![Image text](images/InstalarArch/07.png)

## 8 - Estructura
Le decimos que queremos una estructura por defecto del sistema escogido.
![Image text](images/InstalarArch/08.png)

## 9 - Encriptación
Si queremos podemos encriptar el sistema añadiendo una contraseña. Podemos dejarlo en blanco para que no lo encripte.
![Image text](images/InstalarArch/09.png)

## 10 - Swap
Dependiendo de la potencia de nuestro equipo podemos utilizar una partición de swap.
![Image text](images/InstalarArch/10.png)

## 11 - Nombre de la máquina
Escogemos un nombre para nuestra máquina.
![Image text](images/InstalarArch/11.png)

## 12 - Contraseña root
Escribimos la contraseña para el usuario root.
![Image text](images/InstalarArch/12.png)

## 13 - Nuevo usuario
Añadimos un nombre y una contraseña para crear nuestro usuario.
![Image text](images/InstalarArch/13.png)

## 14 - Sudoers
Escribimos Y para añadir el nuevo usuario a la lista de superusuarios.
![Image text](images/InstalarArch/14.png)

## 15 - Instalación mínima
Seleccionamos la opción 3 para tener una instalación de software mínima.
![Image text](images/InstalarArch/15.png)

## 16 - Drivers
Instalamos los drivers de nuestra tarjeta grafica y de la tarjeta de sonido.
![Image text](images/InstalarArch/16.png)
![Image text](images/InstalarArch/16_2.png)

## 17 - Kernel
Escogemos el kernel que queremos instalar.
![Image text](images/InstalarArch/17.png)

## 18 - Software
Si queremos añadir algún otro programa podemos escribirlo en este moento, separado por comas. Yo aprovecho para instalar un navegador web.
![Image text](images/InstalarArch/18.png)

## 19 - Internet
Necesitamos escoger la interfaz de internet. Tenemos 3 posibilidades: Copiar la misma configuración que tenemos ahora mismo en la instalación, usar NetworkManager para seleccionar una red de forma gráfica, o seleccionar la red enp0s3 que en mi caso es la red cableada.
![Image text](images/InstalarArch/19.png)

## 20 - Hora
Seleccionamos la zona horaria y le decimos que la actualice automaticamente.
![Image text](images/InstalarArch/20.png)

## 21 - Resumen
Ahora nos mostrará un resumen con toda las configuraciones que hemos seleccionado.Una vez estemos conformes y le demos enter comenzará la instalación.
![Image text](images/InstalarArch/21.png)

## 22 - Reiniciar el sistema
![Image text](images/InstalarArch/22.png)