---
title: Preparación para el examen de Gestion de Bases de Datos
tags: [gestionBasesDeDatos, test, bases de datos]
keywords: bases de datos, administracion, gestion
summary: "Test con 41 preguntas para la superación del examen de Gestion de Bases de Datos."
sidebar: mydoc_sidebar
permalink: mydoc_examenes_gestionbbdd.html
folder: mydoc
topnav: topnav
---


## 1. ¿Cuál de las siguientes es una propiedad de los sistemas de información orientados a los datos?
<ol type="a">
    <li>Podemos encontrarnos con datos redundantes e inconsistentes</li>
    <li>Dificultad en el acceso simultáneo de los datos</li>
    <li>Cada aplicación almacena y utiliza sus propios datos</li>
    <li>Los datos se centralizan en una base de datos</li>
</ol>
<H6 align="right">Solución: D</H6>

## 2. Si una entidad A tiene una clave primaria compuesta formada por dos atributos:
<ol type="a">
    <li>Todas son falsas</li>
    <li>La clave ajena relacionada con la entidad A siempre estará formada por los dos atributos de la clave principal</li>
    <li>La clave ajena estará relacionanada con un solo atributo de la clave primaria</li>
    <li>No es posible definir una clave ajena de una entidad que tiene una clave primaria compuesta</li>
</ol>
<H6 align="right">Solución: B</H6>

## 3. Decimos que una relación jerárquica es exclusiva (sin solapamiento) si:
<ol type="a">
    <li>Todas las instancias de las subentidades son de la superentidad</li>
    <li>Una instancia de la superentidad puede tener asociados instancias de cualquiera de las subentidades</li>
    <li>Todas las instancias de la superentidad son de alguna de las subentidades</li>
    <li>Una instancia de la superentidad sólo puede estar asociada a una única instancia de las subentidades</li>
</ol>
<H6 align="right">Solución: D</H6>

## 4. ¿Cuál de los siguientes NO es un requisito para que un atributo sea indentificador o llave?
<ol type="a">
    <li>Tiene que ser el mismo atributo para todos los ejemplares de una entidad</li>
    <li>Tiene que distinguit cada ejemplar de la entidad o relacion</li>
    <li>Puede estar formado por más de un atributo</li>
    <li>Tiene que ser de tipo numérico, a poder ser entero</li>
</ol>
<H6 align="right">Solución: D</H6>

## 5. ¿Cuál de los siguientes NO es un tipo de fragmentación en las bases de datos distribuidas?
<ol type="a">
    <li>Horizontal</li>
    <li>Híbrida</li>
    <li>Vertical</li>
    <li>Modal</li>
</ol>
<H6 align="right">Solución: D</H6>

## 6. ¿Cuál de los siguientes NO es un tipo de usuario dentro de un SGBD?
<ol type="a">
    <li>Administrador</li>
    <li>Usuario interno</li>
    <li>Usuario externo</li>
    <li>Usuario intermedio</li>
</ol>
<H6 align="right">Solución: D</H6>

## 7. El modelo entidad relación para transformar un atributo múltiple al modelo relacional tenemos que:
<ol type="a">
    <li>Crear una nueva tabla con una relación 1 a N con la tabla que contenía el atributo múltiple en el modelo entidad relación</li>
    <li>Crear una nueva tabla con una relación N a M con la tabla que contenía el atributo múltiple en el modelo entidad relación </li>
    <li>Crear una nueva tabla con una relación 1 a 1 con la tabla que contenía el atributo múltiple en el modelo entidad relación</li>
    <li>No es necesario crear ninguna tabla, ya que el modelo relacional permite almacenar atributos con múltiples valores.</li>
</ol>
<H6 align="right">Solución: A</H6>

## 8. Para crear una tabla en una base de datos utilizaré el lenguaje: 
<ol type="a">
    <li>DCL</li>
    <li>DLL</li>
    <li>DML</li>
    <li>DDL</li>
</ol>
<H6 align="right">Solución: D</H6>

## 9. Al pasar una relación N:M entre dos tablas (A y B) del modelo Entidad-Relación al modelo relacional, ¿qué obtenemos?
<ol type="a">
    <li>Tabla A con sus atributos. Tabla B con sus atributos más los de la clave primaria de la entidad A</li>
    <li>Se obtienen tres tablas: Tabla A, Tabla B y Tabla R (la resultante de la relación)</li>
    <li>Tabla A con sus atributos. Tabla B con sus atributos</li>
    <li>Tabla B con sus atributos. Tabla A con sus atributos más los de la clave primaria de la entidad B.</li>
</ol>
<H6 align="right">Solución: B</H6>

## 10. Si queremos borrar un registro de una tabla que tiene relación con registros de la otra tabla, ¿cuál de las siguientes no es una forma de garantizar la integridad referencial?
<ol type="a">
    <li>Eliminar la relación</li>
    <li>Colocar valores nulos en la clave secundaria de la relación</li>
    <li>Prohibir la operación</li>
    <li>Transmitir la operación en cascada</li>
</ol>
<H6 align="right">Solución: A</H6>

## 11. En las relacinoes 1:1 en que las dos entidades tienen el mismo identificador, el paso al modelo relacional nos da...
<ol type="a">
    <li>Una única tabla formada por los atributos de una de las dos entidades</li>
    <li>Dos tablas con sus propios atributos y con una clave secundaria apuntando al identificador de la otra tabla</li>
    <li>Tres tablas: una para cada entidad y una para la relación</li>
    <li>Una única tabla formada por los atributos de las dos entidades</li>
</ol>
<H6 align="right">Solución: D</H6>

## 12. El lenguaje DDL permite:
<ol type="a">
    <li>Creación de copias de seguridad y restauración de las mismas</li>
    <li>Inserción, actualización consulta y eliminación de los datos de una base de datos</li>
    <li>Definir y describir los objetos de la base de datos: creación de tablas, índices</li>
    <li>Definir y describir la seguridad de los datos: privilegios, modos de acceso</li>
</ol>
<H6 align="right">Solución: C</H6>

## 13. Al proceso de introducir datos redundantes de manera que el rendimiento del sistema se optimice se le conoce como:
<ol type="a">
    <li>Integridad referencial</li>
    <li>Distribución de la base de datos</li>
    <li>Persistencia de los datos</li>
    <li>Desnormalización</li>
</ol>
<H6 align="right">Solución: D</H6>

## 14. ¿Cuál de los siguientes atributos en la entidad Persona sería más correcto usar como identificador o llave?
<ol type="a">
    <li>DNI</li>
    <li>Fecha de nacimiento</li>
    <li>Apellidos</li>
    <li>Nombre</li>
</ol>
<H6 align="right">Solución: A</H6>

## 15. En el modelo relacional una clave secundaria es...
<ol type="a">
    <li>Un atributo de una tabla cuyos valores coinciden con los valores de cualquier atributo de otra tabla</li>
    <li>Un atributo de una tabla cuyos valores coinciden con los valores de otra tabla</li>
    <li>Un atributo de una tabla cuyos valores coinciden con los valores de la clave alternativa de otra tabla</li>
    <li>Un atributo de una tabla cuyos valores coinciden con los valores de la clave primaria de otra tabla</li>
</ol>
<H6 align="right">Solución: D</H6>

## 16. Para la creación y asociación de permisos a los usuarios utilizaremos el lenguaje:
<ol type="a">
    <li>DCL</li>
    <li>DML</li>
    <li>DLL</li>
    <li>DDL</li>
</ol>
<H6 align="right">Solución: A</H6>

## 17. Para modificar el DNI de una persona alamacenado en una tabla utilizaré el lenguaje:
<ol type="a">
    <li>DML</li>
    <li>DDL</li>
    <li>DCL</li>
    <li>DLL</li>
</ol>
<H6 align="right">Solución: A</H6>

## 18. ¿Qué ocurre con los atributos que tiene una relación N:M al pasarla al modelo relacional?
<ol type="a">
    <li>Pasan a una de las entidades relacionanadas</li>
    <li>Pasan a una de las entidades relacionadas como claves secundarias</li>
    <li>Pasan a la tabla resultante de la relación</li>
    <li>Se eliminan</li>
</ol>
<H6 align="right">Solución: C</H6>

## 19. Decimos que una relación jerárquica es total si:
<ol type="a">
    <li>Todas las instancias de la superentidad son de alguna de las subentidades</li>
    <li>Una instancia de la superentidad sólo puede estar asociada a una única instancia de las subentidades</li>
    <li>Una instancia de la seuperentidad puede tener asociadas instancias de cualquiera de las subentidades</li>
    <li>Todas las instancias de las subentidades son de la superentidad</li>
</ol>
<H6 align="right">Solución: A</H6>

## 20. Al esquema teórico de los datos (descripción y relaciones) de una base de datos se le conoce como...
<ol type="a">
    <li>Nivel externo</li>
    <li>Nivel interno</li>
    <li>Nivel físico</li>
    <li>Nivel conceptual</li>
</ol>
<H6 align="right">Solución: D</H6>

## 21. Dada una entidad que se relaciona con otras dos, pero sólo con una de ellas a la vez, ¿qué tipo de relacion debemos crear? 
<ol type="a">
    <li>Relación jerárquica</li>
    <li>Relación N:M</li>
    <li>Relación exclusiva</li>
    <li>Relación refleciva</li>
</ol>
<H6 align="right">Solución: C</H6>

## 22. Al conjunto de todos los valores posibles que puede tomar un determinado atributo se le conoce como...
<ol type="a">
    <li>Grado</li>
    <li>Cardinalidad</li>
    <li>Dominio</li>
    <li>Clave</li>
</ol>
<H6 align="right">Solución: C</H6>

## 23. Si una entidad A tiene una clave primaria compuesta formada por dos atributos:
<ol type="a">
    <li>Todas son falsas</li>
    <li>La clave ajena estará relacionada con un solo atributo de la clave primaria</li>
    <li>La clave ajena relacionada con la entidad A siempre estará formada por los dos atributos de la clave principal</li>
    <li>No es posible definir una clave ajena de una entidad que tiene una clave primaria compuesta</li>
</ol>
<H6 align="right">Solución: C</H6>

## 24. ¿A qué nos referimos con integridad de la clave?
<ol type="a">
    <li>Que una clave no puede tener valores repetidos</li>
    <li>Que sus valores sólo podrán ser los que contenga la clave primaria de la tabla con la que se relaciona</li>
    <li>Que una clave no puede cambiar su valor a lo largo del tiempo</li>
    <li>Que una clave no puede tener valores nulos</li>
</ol>
<H6 align="right">Solución: D</H6>

## 25. ¿Cuál de las siguientes NO sería una función de un administrador de bases de datos?
<ol type="a">
    <li>Realización de copias de seguridad</li>
    <li>Control del espacio en disco</li>
    <li>Resolución de emergencias</li>
    <li>Programación de las aplicaciones para acceder a los datos</li>
</ol>
<H6 align="right">Solución: D</H6>

## 26. Una entidad débil se caracteriza por:
<ol type="a">
    <li>No tener ninguna relación con otras entidades</li>
    <li>Todos sus atributos son candidatos</li>
    <li>Depender de la existencia de una entidad fuerte</li>
    <li>No admiten relación con otras entidades</li>
</ol>
<H6 align="right">Solución: C</H6>

## 27. Un registro esta formado por... 
<ol type="a">
    <li>Tablas</li>
    <li>Campos</li>
    <li>Ficheros</li>
    <li>Instancias</li>
</ol>
<H6 align="right">Solución: B</H6>

## 28. En el caso de las entidades Jugador y Equipo, en el que un jugador sólo puede estar en un equipo y un equipo puede tener 6 jugadores, la cadinalidad de esta relación sería...
<ol type="a">
    <li>1:5</li>
    <li>1:N</li>
    <li>1:1</li>
    <li>N:M</li>
</ol>
<H6 align="right">Solución: B</H6>

## 29. A los programas que se ejecutan automáticamente cuando se cumple una determinada condición se les llama...
<ol type="a">
    <li>Tuplas</li>
    <li>Reglas de integridad</li>
    <li>Disparadores o triggers</li>
    <li>Reglas de validación</li>
</ol>
<H6 align="right">Solución: C</H6>

## 30. El modelo de base de datos cliente-servidor es...
<ol type="a">
    <li>Un sistema distribuido siempre</li>
    <li>Un sistema centralizado siemrpe</li>
    <li>Un sistema distribuido ya que se reparten los procesos entre clientes y servidor</li>
    <li>Un sistema centralizado si se dispone de un único servidor de bases de datos</li>
</ol>
<H6 align="right">Solución: D</H6>

## 31. Si todos los atributos de una tabla son indivisibles (atómicos) decimos que esa tabla está en...
<ol type="a">
    <li>La cuarta forma normal</li>
    <li>La tercera forma normal</li>
    <li>La segunda forma normal</li>
    <li>La primera forma normal</li>
</ol>
<H6 align="right">Solución: D</H6>

## 32. ¿Cuál de las siguientes afirmaciones es falsa?
<ol type="a">
    <li>Una entidad tiene existencia propia</li>
    <li>Las entidades de un mismo tipo están definidas en base a un mismo conjunto de atributos</li>
    <li>Una entidad es distinguible del resto de entidades del sistema</li>
    <li>Una entidad tiene diferentes atributos definidos para cada una de sus instancias</li>
</ol>
<H6 align="right">Solución: D</H6>

## 33. Al pasar una relación 1:N entre dos tablas (A y B) del modelo Entidad-Relación al modelo relacional, ¿qué obtenemos?
<ol type="a">
    <li>Se obtienen tres tablas: Tabla A, Tabla B y Tabla R (la resultante de la relación</li>
    <li>Tabla B con sus atributos. Tabla A con sus atributos más los de la clave primaria de la entidad B</li>
    <li>Tabla A con sus atributos. Tabla B con sus atributos más los de la clave primaria de la entidad A</li>
    <li>Tabla A con sus atributos. Tabla B con sus atributos</li>
</ol>
<H6 align="right">Solución: C</H6>

## 34. ¿Qué tenemos que hacer con los atributos múltiples al pasarlos del modelo Entidad-Relación al modelo relacional?
<ol type="a">
    <li>Eliminarlos y crear diversos atributos simples</li>
    <li>Eliminarlos dejando sólo uno</li>
    <li>Eliminarlos y crear una nueva entidad</li>
    <li>Dejarlos tal y como están</li>
</ol>
<H6 align="right">Solución: C</H6>

## 35. El modelo de base de datos que usa una estructura de árbol para guardar los datos se conoce como...
<ol type="a">
    <li>Modelo relacional</li>
    <li>Modelo dicotómico</li>
    <li>Modelo jerárquico</li>
    <li>Modelo de red</li>
</ol>
<H6 align="right">Solución: C</H6>

## 36. ¿Qué es el grado de una relación?
<ol type="a">
    <li>El tamaño en base al número de atributos de una tabla</li>
    <li>El tamaño de base al número de filas de una tabla</li>
    <li>El tamaño de base al número de tuplas de una tabla</li>
    <li>El tamaño de base al número de registros de una tabla</li>
</ol>
<H6 align="right">Solución: A</H6>

## 37. MongoDB es una base de datos de tipo:
<ol type="a">
    <li>De red</li>
    <li>Objeto-relacional</li>
    <li>Relacional</li>
    <li>No-relacional o NoSQL</li>
</ol>
<H6 align="right">Solución: D</H6>

## 38. A los atributos formados a su vez por otros atributos se les conoce como...
<ol type="a">
    <li>Atributos débiles</li>
    <li>Atributos múltiples</li>
    <li>Atributos fuertes</li>
    <li>Atributos compuestos</li>
</ol>
<H6 align="right">Solución: D</H6>

## 39. ¿Cuál de las sisguientes NO es una propiedad de los ficheros secuenciales de acceso indecado?
<ol type="a">
    <li>Requieren una estructura adicional</li>
    <li>Se generan índices de los campos por los que se van a realizar más accesos</li>
    <li>La inserción de registros no se hace secuencialemnte al final del fichero</li>
    <li>Mejoran el rendimiento del acceso de los datos</li>
</ol>
<H6 align="right">Solución: C</H6>

## 40. El diccionario de una base de datos contiene
<ol type="a">
    <li>Es una copia de seguridad de la base de datos</li>
    <li>Información que describe los datos de la base de datos (metadatos)</li>
    <li>Contiene los datos introducidos por el usuario, por ejemplo, los datos de un trabajador</li>
    <li>El copyright de la base de datos</li>
</ol>
<H6 align="right">Solución: B</H6>

## 41. En el modelo relacional el concepto de clave candidata corresponde a:
<ol type="a">
    <li>Es la clave principal de una entidad</li>
    <li>Conjunto de atributos que identifican inequívocamente cada tupla de una relación. Una relación puede tener múltiples claves candidatas</li>
    <li>Conjunto mínimo de atributos que me identifican inequívocamente cada tupla de una entidad. Una entidad solo puede tener una clave candidata</li>
    <li>Uno o varios atributos del mismo tipo que me identifican inequívocamente cada tupla de una entidad</li>
</ol>
<H6 align="right">Solución: B</H6>