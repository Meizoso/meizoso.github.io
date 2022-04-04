---
title: Nmap
tags: [software, nmap]
keywords: software, nmap
summary: "Tablas de comandos nmap y ejemplos de usos."
sidebar: mydoc_sidebar
permalink: mydoc_reco_nmap.html
folder: mydoc
topnav: topnav
---

## 1. Descubrimiento de equipos

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-Pn</b> | No ping | No realiza ninguna técnica de descubrimiento. Pasa directamente al análisis de puertos. |
| <b>-sL</b> | List scan | Sólo lista quipos. No envía ningún paquete a los objetivos. |
| <b>-sn</b> | Ping sweep | Implica un -PE + -PA 80 + -PS 443. |
| <b>-PR</b> | Ping ARP | Envía un ARP Request. | Sólo para objetivos en nuestra red local |
| <b>-PS[puertos]</b> | Ping TCP SYN | Envia un SYN. Se puede indicar lista de puertos. | Por defecto lo hace al puerto 80. |
| <b>-PA[puertos]</b> | Ping TCP ACK | Envia un ACK vacío. Se puede indicar lista de puertos. | Por defecto lo hace al puerto 80. |
| <b>-PU[puertos]</b> | Ping UDP | Envia un UDP vacío. Se puede indicar a que puerto. Por defecto lo hace al puerto 31338. | Traspasa cortafuegos que sólo filtran TCP.
| <b>-PY[puertos]</b> | Ping SCTP | Envía un paquete SCTP INIT. Se puede indicar lista de puertos | Por defecto envía al puerto 80.
| <b>-PE</b> | Ping ICMP echo | Envía un ICMP Echo Request. | Poco fiable. Filtrado en la mayoría de firewalls |
| <b>-PP</b> | Ping ICMP Timestamp | Envía un ICMP Timestamp Request | Muchos cortafuegos no filtran este ICMP |
| <b>-PM</b> | Ping ICMP Address mask | Envía un ICMP Address Mask Request. | Muchos cortafuegos no filtran este ICMP |
| <b>-PO[proto]</b> | IP protocol ping | Envia diferentes paquetes usando los portocolos IP 1, 2 y 4 |

## 2. Modificadores

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-n</b> | DNS | No realiza resolución inversa de DNS | Más sigiloso y rápido. |
| <b>-R</b> | DNS | Realiza un resolución DNS incluso a objetivos que aparecen como "down". |
| <b>--dns-servers[servers]</b> | DNS | Especifica la lista de servidores DNS a utilizar para hacer la resolución. |
| <b>--system-dns</b> | DNS | Utiliza el sistema de resolución DNS del sistema operativo. |
| <b>--traceroute</b> | Ruta | Descubre la ruta seguida por los paquetes hasta el equipo objetivo. |

## 3. Análisis de puertos

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-sT</b> | Connect | Envia un SYN, luego un RST para cerrar la conexión. | Se utilizan llamadas del SO. Menos eficiente que SYN Stealth |
| <b>-sS</b> | SYN Stealth/Half-open scan | Envía un SYN. | Técnica usada por defecto. Rápida, fiable y relativamente sigilosa. |
| <b>-sU</b> | UPD Scan | Envía un UPD vacío. | Más lento que un análisis TCP. Se puede realizar en paralelo a otras técnicas. Para diferenciar entre OPEN y FILTERED se puede usar el detector de versiones (-sV). |
| <b>-sI</b> | Idle Scan | Usa IP origen de un equipo intermedio (Zombie) para analizar el objetivo. Según los cambios en el IPID del zombie, se deduce el setado de los puertos del objetivo. | Técnica avanzada y sigilosa. No queda registro de ningún paquete directo al objetivo. |
| <b>-sA</b> | TCP ACK | Envía ACK vacío. | Solo determina si los puertos están o no filtrados. |
| <b>-sN</b> | TCP NULL | Envía TCP con todos los flags a 0. |  |
| <b>-sF</b> | TCP FIN | Envía TCP con el flag FIN a 1. |  |
| <b>-sX</b> | XMas Scan | Envía TCP con los flags FIN, PSH y URG a 1. |  |
| <b>-sM</b> | TCP Maimon | Envía un ACK con el flag FIN a 1 |  |
| <b>-sW</b> | TCP Window | Envía ACK vacío. Dieferencia entre puertos open y closed. | No siempre es fiable. |
| <b>--scanflags[flags]</b> | TCP Personal | Envía TCP con los flags que se indiquen. Por defecto, trata estado de puertos como lo hace -sS, pero se puede especificar otro scan. | Flags posibles: URG, ACK, PSH, RST, SYN y FIN. |
| <b>-sO</b> | IP Protocol | Envía paquetes IP con una cabecera vacía (excepto para TCP, UDP y ICMP) iterando sobre el campo IP Protocol. | Determina los protocolos de transporte soportados por el objetivo. |
| <b>-sY</b> | SCTP INIT | Envía paquetes SCTP INIT (inicio conexión). | Equivalente a TCP SYN |
| <b>-sZ</b> | SCTP Cookie Echo | Envía paquetes SCTP Cookie Echo (3ª fase de conexión). | Útil si hay cortafuegos sin estado. |
| <b>-b [ftpsrv]</b> | FTP Bounce | Usa la funcionalidad Proxy-FTP para recorrer puertos del objetivo. Las respuestas FTP indican estado del puerto. Parámetro: username:pwd@server:port | Explota las conexiones Proxy-FTP, poco extendidas. Se usa para traspasar cortafuegos. |


## 4. Especificación de puertos

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-F</b> | Fast mode | Escanea los puertos más comunes. |  |
| <b>-r</b> |  | Los puertos se escanean en orden secuencial creciente. |  |
| <b>-p[rango]</b> |  | Especifica el rango de puertos a escanear. -p- escanea todos los puertos. U: indica sólo UDP; T: sólo TCP; S: sólo SCTP | Ej: -p U:53,111,T:21-25,80,139,S:9 |
| <b>--top-ports[num]</b> |  | Escanea los [num] puertosmás comunes. |  |
| <b>--port-ratio[ratio]</b> |  | Escanea los puertos cuyo ratio de uso se superio a [ratio] |  |

## 5. Detección de versiones

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-sV</b> |  | Interroga al conjunto de puertos abiertos detectados para tratar de descubrir servicios y versiones en puertos abiertos. |  |
| <b>--allports</b> |  | Incluye todos los puertos en la fase de detección de versiones. Por defecto se excluyen algunos. |  |
| <b>--version-intensity[num]</b> |  | Intensidad con que se realizan pruebas para comprobar servicios y versiones disponibles. Valores de 0 (ligera) a 9 (todas las pruebas disponibles). |  |
| <b>--version-light</b> |  | Alias de --version-intensity 2 |  |
| <b>--version-all</b> |  | Alias de --version-intensity 9 |  |
| <b>--versión-trace</b> |  | Muestra traza de actividad del análisis de versiones y servicios. |  |

## 6. Detección de sistema operativo

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-O</b> |  | Envía paquetes TCP y UDP al objetivo. Analiza las respuestas para conocer qué tipo de implementación de la pila TCP/IP tiene el objetivo. |  |
| <b>--osscan-limit</b> |  | Limita la detección del SO a objetivos prometedores. |  |
| <b>--osscan-guess</b> |  | Realiza un proceso más agresivo para la detección del SO. |  |
| <b>--max-os-tries</b> |  | Fija máximo de intentos para detectar el SO. | Por defecto 5 intentos. |

## 7. Evasión de cortafuegos/IDS y Spoofing

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-f</b> | Fragmentar paquetes | Divide los paquetes en fragmentos de 8 bytes después de la cabecera IP. Cada f extra aumenta en 8 bytes más el tamaño de los fragmentos. | Usado para dividir las cabeceras TCP y complcar su análisis. |
| <b>--mtu</b> | Fragmentar paquetes | Especifica el tamaño desedo. En múltiplos de 8 bytes. | Usado para dividir las cabeceras TCP y complcar su análisis. |
| <b>--data-length</b> | Tamaño del paquete | Añade datos aleatorios a los paquetes enviados. Por defecto las sondas se manda vacías. | Usado debido a que un paquete no vacío es menos sospechoso. |
| <b>--radomize-hosts</b> | Objetivos aleatorios | Divide la lista de objetivos en grupos de hasta 16384 equipos y los analiza en un orden aleatorio. | Evita flujo de paquetes hacia IP consecutivas (suele se sospechoso). |
| <b>-D[host1][,[hostN]]</b> | Señuelos | Permite especificar un conjunto de IP válidas que se usarán como dirección origen en el análisis a modo de señuelos. Las respuestas de los objetivos llegarán también a los señuelos | Usado para enmascarar la propia IP en el escaneo y dificultar la traza de origen. Los señuelos deben estar activos. |
| <b>-S [IP]</b> | Falsear dirección de origen | Envía paquetes IP con la dirección de origen especificada. | Algunos ISP filtran las IP de origen falseadas. No se reciben respuestas. |
| <b>--spoof-mac [mac]</b> | Falsear dirección de origen | Envía tramas Ethernet con la dirección de origen especificada. Si no se especifica completa el resto se completa de forma aleatoria. |  |
| <b>-g [port]</b> | Falsear puerto de origen | Envía paquetes usando el puerto especificado, cuando sea posible. | Usado porque muchos cortafuegos aceptan conexiones entrantes a puertos típicos como TCP20 ó UDP53. |
| <b>--source port</b> | Falsear puerto de origen | Envía paquetes usando el puerto especificado, cuando sea posible. | Usado porque muchos cortafuegos aceptan conexiones entrantes a puertos típicos como TCP20 ó UDP53. |
| <b>-e [iface]</b> | Definir interfaz | Define la interfaz de red en caso de existir múltiples. |  |
| <b>--ip-options[opt]</b> | Opciones IP | Permite fijar opciones del protocolo IP. Routers bloquean muchas de ellas. Útil para definir o reconocer rutas. |  |
| <b>--ttl [valor]</b> | TTL | Fija el tiempo de vida de las sondas enviadas. |  |
| <b>--badsum</b> | Checksums incorrectos | Usa checksum inválidos para TCP, UDP y SCTP. | Usado porque muchos cortafuegos/IDS no procesan este campo y los objetivos si. |
| <b>--adler32</b> | SCTP Checksum | Utiliza metodo de cálculo de resumen Adler32, en lugar del actual CRC-32C, para paquetes SCTP. | Útil para obtener respuestas de implementaciones SCTP antiguas. |

## 8. Temporización y rendimiento

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>--min-hostgroup [num]</b> | Objetivos en paralelo | Establece los límites mínimo y máximo que se pueden analizar de forma concurrente. |  |
| <b>--max-hostgroup [num]</b> |  |  |  |
| <b>--min-parallelism [num]</b> | Pruebas en paralelo | Establece los límites mínimo y máximo de pruebas que pueden estar llevándose a cabo de forma concurrente. | Útil en redes o equipos lentos. Valor demasiado alto puede afectar a la precisión. |
| <b>--max-parallelism [num]</b> |  |  |  |
| <b>--min-rtt-timeout [time]</b> | Tiempo de respuesta de las sondas | Modifica el tiempo de espera de respuestas enviadas a sondas enviadas. Si vence el tiempo de espera, Nmap considera que no hay respuesta y sigue con la siguiente sonda. Por defecto valor dinámico basado en el tiempo de sondas anteriores. | Útil en redes rápidas o cuando muchos puertos están cerrados. |
| <b>--max-rtt-timeout [time]</b> |  |  |  |
| <b>--initial-rtt-timeout [time]</b> |  |  |  |
| <b>--max-retries [num]</b> | Retransmisiones | Especifica el número de retransmisiones para cada sonda. | Por defecto 10 reintentos. |
| <b>--host-timeout [time]</b> | Tiempo de análisis de equipo | Especifica el tiempo máximo que ocupa nmap en el análisis de un equipo completo. Si vence este tiempo, no se muestra nada sobre el mismo en el análisis final | Útil para análisis grandes en redes poco fiables o lentas, a costa de perder algunos resultados. |
| <b>--scan-delay [time]</b> | Tiempo entre sondas | Define el tiempo inicial y máximo que espera nmap entre cada prueba. | Útil si la red limita la tasa de transferencia o de respuestas. |
| <b>--max-scan-delay [time]</b> |  |  |  |
| <b>--min-rate [num]</b> | Tasa de envío de sondas | Controla la tasa de envío de sondas. |  |
| <b>--max-rate [num]</b> |  |  |  |
| <b>--defeat-rst-ratelimit</b> | Límite de respuestas RST | Muchos equipos limitan, además del número de ICMP, el número del RST que envían. Por defecto nmap se ajusta al límite. Este parámetro hace que nmap no tenga en cuenta este límite. | Puede reducir precisión. |
| <b>--nsock-engine [motor]</b> | Moto E/S nsock | Fuerza el uso de un motor de control de entrada salida. | Valores posibles: epoll y select |
| <b>-T[plant]</b> | Plantillas de tiempo | Define una plantilla genérica de tiempos, que configura varios de los parámetros vistos anteriormente. | Valores de + a - lento: paranoid(T0), sneaky(T1), polite(T2), normal(T3), aggressive(T4), insane(T5) |

## 9. Scripting

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-sC</b> |  | Incluye en el análisis actual el conjunto por defecto de scripts (algunos pueden ser intrusivos) | Equivalente a: --script default |
| <b>--script [valor]</b> |  | Define los scripts a utilizar. Valor puede ser un nombre de fichero, categoria, directorio, expresión, etc. Alias all ejecuta todos los scripts (peligroso) | Valores separados por comas. Prefijo + hace que se ejecuten aunque no corresponda. |
| <b>--script-args [args]</b> |  | Argumentos a pasar a lios scripts. Formato: [nombre]=[valor] | Argumentos separados por comas. Prioridad sobre los definidos en fichero. |
| <b>--script-args-file [file]</b> |  | Carga argumentos de un fichero. |  |
| <b>--scritp-help [valor]</b> |  | Muestra ayuda sobre los scripts. |  |
| <b>--script-trace</b> |  | Símil de --packet-trace una capa ISO por encima. Muestra todas las comunicaciones realizadas por un script. |  |
| <b>--script-updatedb</b> |  | Actualiza la base de datos de scripts. |  |

## 10. Especificación de objetivos

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-iL [fich]</b> | Objetivos en fichero | Se pasan los objetivos en un fichero, cada uno en una línea. |  |
| <b>-iR [num]</b> | Objetivos aleatorios | Elige los objetivos de forma aleatoria. |  |
| <b>--exclude [hosts]</b> | Lista de exclusión | Indica equipos a excluir del análisis. |  |
| <b>--exclude [fich]</b> | Fichero de exclusión | Se pasan por un fichero los equipos a excluir del análisis. |  |

## 11. Salida

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-oN [file]</b> | Salida normal | Guarda en un fichero una salida muy similar a la mostrada por pantalla en modo interactivo. |  |
| <b>-oX [file]</b> | Salida XML | Guarda la salida en un fichero XML .|  |
| <b>-oS</b> | Salida Script Kiddie | Salida muy similar a la del modo interactivo pero sustituyendo carácteres y capitalización. |  |
| <b>-oG</b> | Salida grepable | Salida facilmente tratable con el comando grep. |  |
| <b>-oA [patrón]</b> | Salida en todos los formatos. | Crea un fichero para todos los tipos de salida. |  |
| <b>-v</b> | Verbosidad | Aumenta la cantidad de información sobre el progreso del análisis que se muestra por pantalla. | Más v muestra una mayor verbosidad. |
| <b>-d</b> | Depuración | Añade información de depuración a la salida que Nmap muestra por pantalla. | Más p muestra más infroación |
| <b>--reason</b> | Razón | Indica la razón por la que se ha concluido el estado de un puerto o equipo. | Permite diferenciar el tipo de respuestas que ha generado un puerto cerrado. |
| <b>--stats-every [time]</b> | Estadísticas | Indica cada cuanto tiempo se imprimen estadísticas sobre el tiempo restante del análisis. |  |
| <b>--packet-trace</b> | Traza de paquetes | Imprime información sobre cada paquete que se envía o recibe. | Incluye información de --version-trace y --script-trace |
| <b>--open</b> | Puertos abiertos | Muestra solo los puertos que están abiertos. |  |
| <b>--iflist</b> | Interfaces y rutas | Muesta únicamente el listado de interfaces y de rutas detectado. | Útil para depuración. |
| <b>--log-errors</b> | Errores | Guarda los errores generados durante la ejecución y los muestra por pantalla. |  |
| <b>--append-output</b> | Ficheros de salida | Instruye a nmap para aladir los resultados del análisis actual a un fichero de salida existente, en lugar de borrar el contenido de dicho fichero. | Puede causar problemas con archivos XML. |
| <b>--resume [file]</b> | Continuar | Continúa un análisis en el punto en que se quedó, si se indica como parámetro un fichero generado con los modificadores -oN o -oG |  |
| <b>--stylesheet [file]</b> | Hoja de estilos | Indica que hoja de estilos XSL incrutar en la salida XML. |  |
| <b>--webxml</b> | Hoja de estilos | Alias para --stylesheet http://nmap.org/svn/docs/nmap.xsl |  |
| <b>--no-stylesheet</b> | Hoja de estilos | Indica que no se incruste ningún enlace a hoja d estilos en la salida XML. |  |

## 12. Miscelánea

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>-6</b> | IPv6 | Habilita el análisis de redes IPv6. |  |
| <b>-A</b> | Análisis agresivo | Alias para -O -sV -sC --traceroute. |  |
| <b>--datadir [dir]</b> | Directorio de datos | Indica el directorio donde Nmap lee algunos ficheros que necesita para su uso. |  |
| <b>--servicedb [file]</b> | Fichero de servicios | Indica una localización personalizada para el fichero donde Nmao obtiene la información sobre servicios. |  |
| <b>--versiondb [file]</b> | Fichero de versiones | Indica la ubicación del ficheri de donde Nmap obtiene las sondas que debe enviar para detectar servicios (-sV). |  |
| <b>--send-eth</b> | Escribir en tramas ethernet | Escribe directamente tramas a nivel ethernet sin usar el API de red ni transporte. | Usado para evitar limitaciones de algunas implentaciones de la pila TCP/IP. Activada por defecto en la versión de windows. |
| <b>--send-ip</b> | Escribir tramas IP | Escribe paquetes a nivel IP, y los pasa al SO para que este se encarge de enviarlos. | Complementaria a la opción anterior. |
| <b>--privileged</b> | Modo privilegiado | Asume que tiene suficientes permisos para realizar operaciones que requieren elevación de privilegios. |  |
| <b>--unprivileged</b> | Modo sin privilegios | Opuesto a --privileged |  |
| <b>--release-memory</b> | Liberar memoria | Hace que Nmap libere toda su memoria antes de finalizar su ejecución. | Facilita el descubrimiento de filtraciones de memoria. |
| <b>-v / --version</b> | Versión | Imprime la versión de Nmap. |  |
| <b>-h / --help</b> | Ayuda | Imprime la página de ayuda. |  |

## 13. Interacción en tiempo de ejecución

| Opción | Nombre | Funcionamiento | Observaciones |
|--------|--------|----------------|---------------|
| <b>v / V</b> |  | Aumenta / disminuye el nivel de verbosidad. |  |
| <b>d / D</b> |  | Aumenta / disminuye la cantidad de información de depuración que se muestra. |  |
| <b>p / P</b> |  | Activa / desactiva la traza de paquetes (--pack-trace) |  |
| <b>?</b> |  | Muestra la pantalla de ayuda de interacción en timepo de ejecución. |  |

## Ejemplos de uso
### Escaneo básico
{% include callout.html content="nmap 192.168.1.56" type="primary" %}

<!--TERMINAL-->
<link href="css/miEstilo.css" rel="stylesheet" type="text/css">
<div id="barra"><img src="images/terminal/botones.png" id="botones"><center id="texto_barra">meizoso.github.io</center></div>
<div id="terminal">
>$ nmap 192.168.1.56<br/>
Starting Nmap 7.80 ( https://nmap.org ) at 2022-04-04 13:13 CEST<br/>
Nmap scan report for mx.home (192.168.1.56)<br/>
Host is up (0.000099s latency).<br/><br/>
Not shown: 998 closed ports<br/>
PORT     STATE SERVICE<br/>
111/tcp  open  rpcbind<br/>
6566/tcp open  sane-port<br/>

Nmap done: 1 IP address (1 host up) scanned in 0.06 seconds<br/></div>
<br/>