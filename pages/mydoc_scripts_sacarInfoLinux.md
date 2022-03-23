---
title: Script para extraer información de un sistema Linux
tags: [script, Linux]
keywords: script, Linux, so
summary: "Script para extraer información de un sistema Linux"
sidebar: mydoc_sidebar
permalink: mydoc_script_sacarInfoLinux.html
folder: mydoc
topnav: topnav
---
## 1. Código

```shell
#!/bin/bash
echo '#######################'
echo '## SISTEMA OPERATIVO ##'
echo '#######################'
echo ''
cat /etc/issue && cat /etc/*-release
echo ''
echo ''
echo '############'
echo '## KERNEL ##'
echo '############'
echo ''
uname -a
echo ''
echo ''
echo '#######################'
echo '## CONFIGURACION RED ##'
echo '#######################'
echo ''
ip addr
echo ''
echo ''
echo '########################'
echo '## TABLA ENRUTAMIENTO ##'
echo '########################'
echo ''
route -n
echo ''
echo ''
echo '##############'
echo '## USUARIOS ##'
echo '##############'
echo ''
cat /etc/passwd
echo ''
echo ''
echo '############################'
echo '## USUARIOS CON UID Y GID ##'
echo '############################'
echo ''
for user in $(cat /etc/passwd | cut -f1 -d":"); do id $user; done
echo ''
echo ''
echo '#######################'
echo '## INICIOS DE SESION ##'
echo '#######################'
echo ''
lastlog
echo ''
echo ''
echo '################################'
echo '## USUARIOS CON PERMISOS ROOT ##'
echo '################################'
echo ''
cat /etc/passwd | cut -f 1,3,4 -d ":" | grep 0:0
echo ''
echo ''
echo '#############'
echo '## SUDOERS ##'
echo '#############'
echo ''
cat /etc/sudoers
echo ''
echo ''
echo '###################'
echo '## TRABAJOS CRON ##'
echo '###################'
echo ''
cat /etc/crontab && ls -als /etc/cron*
echo ''
echo ''
echo '###################################'
echo '## TRABAJOS CRON WORLD-WRITEABLE ##'
echo '###################################'
echo ''
find /etc/cron* -type f -perm -o+w -exec ls -l {} \;
echo ''
echo ''
echo '###########################'
echo '## PROCESOS EN EJECUCIÓN ##'
echo '###########################'
echo ''
ps auxwww
echo ''
echo ''
echo '#####################################'
echo '## ARCHIVOS SUID CON PERMISOS ROOT ##'
echo '#####################################'
echo ''
find / -uid 0 -perm -4000 -type f 2>/dev/null
echo ''
echo ''
echo '###########################################'
echo '## ARCHIVOS CON PERMISOS WORLD-WRITEABLE ##'
echo '###########################################'
echo ''
find -perm -2 -type f 2>/dev/null
echo ''
echo ''
echo '###################'
echo '## ARCHIVOS GUID ##'
echo '###################'
echo ''
find / -perm -2000 -type f 2>/dev/null
echo ''
echo ''
echo '##########################'
echo '## SISTEMAS DE ARCHIVOS ##'
echo '##########################'
echo ''
df
````

## 2. Explicación

{% include callout.html content="
&nbsp;&nbsp;&nbsp;&nbsp;**cat /etc/issue && cat /etc/*-release** → Ver información del sistema operativo<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**uname -a** → Ver información del Kernel<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**ip addr** → Configuración de red<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**route -n** → Tabla de enrutamiento<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**cat /etc/passwd** → Usuarios<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**for user in $(cat /etc/passwd | cut -f1 -d":"); do id $user; done** → Usuarios con UID y GID<br/><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**lastlog** → Últimos inicios de sesión<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**cat /etc/passwd | cut -f 1,3,4 -d ":" | grep 0:0** → Usuarios con permisos de administrador<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**sudoers** → Archivo sudoers<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**cat /etc/crontab && ls -als /etc/cron*** → Trabajos de CRON<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**find /etc/cron* -type f -perm -o+w -exec ls -l {} \;** → Trabajos CRON World-Writeable<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**find / -perm -2000 -type f 2>/dev/null** → Archivos GUID<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**df** → Sistemas de archivos<br/>
" type="primary" %}

