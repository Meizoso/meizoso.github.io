---
title: Descargando documentos de Scribd
tags: [hacking, scribd]
keywords: hacking, scribd
summary: "En esta ocasión veremos como es posible descargar PDFs de la web Scribd sin registrarse."
sidebar: mydoc_sidebar
permalink: mydoc_hacking_scribd.html
folder: mydoc
topnav: topnav
---


{% include warning.html content="Todas las técnicas aqui usadas son solo con el propósito de educar. En ningún caso se incita al lector a usarlas con fines maliciosos o ilegales."%}

## 1. Explicación del caso

Todos conocemos el popular sitio **scribd.com** en el cual se pueden visualizar libros y documentos. Esta vez me centraré en los documentos. Estos documentos suelen estar protegidos y solo puedes ver unas pocas primeras páginas, también se te da la opción de subir un archivo propio y acambio te habilitan la lectura y descarga del mismo, pero... ¿Y si te dijera que se pueden ver los documentos enteros sin registrarse ni usar páginas con mil anuncios?

<img src="/images/scribd/scribd1.png"><br/><br/><br/>

## 2. En la url esta el secreto

Después de visitar varias páginas que te transforman un enlace de Scribd a un documento pdf (todo con un fin científico) me puse a la tarea de investigar como estas páginas funcionaban.

Halle que con modificar un poco la url se puede ver el PDF en forma de imágenes. Tan solo debemos apuntar el número del documento y modificar la url de la siguiente forma: **https://www.scribd.com/embeds/NUMERO-DOC/content?start_page=1**

<img src="/images/scribd/scribd2.png"><br/><br/><br/>

## 3. Descargando la página

Vale, ahora ya podemos ver el documento completo, pero sigue estando en la web y no simpre vamos a tener internet por lo que supongamos que queremos descargarlo. Yo he creado el siguiente script para facilitarme la vida:

```shell
#!/bin/bash
case $1 in
    "-d")
        wget -O $3 --header="Accept: text/html" --user-agent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10.8; rv:21.0) Gecko/20100101 Firefox/21.0" --referer 'html.scribdassets.com' https://www.scribd.com/embeds/$2/content?start_page=1 ;;
    "-o")
        open "https://www.scribd.com/embeds/$2/content?start_page=1" ;;
esac
````
### Explicación del comando **wget**

| Parámetros | Significado
|-------|--------
| <center><b>-O</b></center> | Indica el nombre con el que se guarda el archivo.
| <center><b>--header</b></center> | Modificamos la cabecera para indicar el tipo de contenido que puede comprender el cliente.
| <center><b>--user-agent</b></center> | Modificamos la cabecera para darle a entender a la página que somos un sistema y software en específico.
| <center><b>--referer</b></center> | Solución contra protección de enlaces activos.

### Dónde podemos encontrar el **--referer** de una web

Primero le damos clic derecho en la web y pulsamos **inspeccionar**.

Una vez abierto el menú vamos a la pestaña **Network** y pulsamos **F5** para recargar la web.

Ahora en la lista que nos aparace buscamos un recurso que este en la web, una imagen por ejemplo.

<img src="/images/scribd/scribd3.png"><br/><br/><br/>

Podemos verlo abajo en **Request Headers** > **Host**

<img src="/images/scribd/scribd4.png"><br/><br/><br/>