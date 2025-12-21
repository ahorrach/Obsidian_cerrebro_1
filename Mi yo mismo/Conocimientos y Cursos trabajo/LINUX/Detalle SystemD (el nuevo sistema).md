
 Systemd es el sistema de inicio adoptado por las principales distribuciones desde 2015 .  Utiliza un único programa que emplea ficheros de configuración para cada elemento gestionado .

### Unidades (Units)
 Systemd gestiona el sistema mediante diferentes tipos de unidades :
* **service**: Para gestionar servicios o demonios.
*  **target**: Agrupaciones de unidades que definen estados del sistema (equivalentes a runlevels) .
* **socket**: Para la comunicación entre procesos.
*  **device, mount, automount, path, snapshot**: Otros tipos de gestión de recursos.

### Ubicación de los Ficheros de Unidad
 Los ficheros se definen con el nombre de la unidad y su tipo como extensión (ej: `ssh.service`) .  Se encuentran en:
* `/etc/systemd/system/` (Configuraciones locales/administrador).
* `/lib/systemd/system/` o `/usr/lib/systemd/system/` (Configuraciones por defecto del sistema/paquetes).

### Estructura de un Fichero de Unidad (Ejemplo .service)
 Un fichero de servicio (como `syslog.service`) se divide en secciones:
*  **[Unit]**: Contiene la descripción, documentación y dependencias (`Requires`, `After`, `Conflicts`) .
* **[Service]**: Define el comportamiento del proceso:
    *  `Type`: Tipo de inicio (ej: `notify`) .
    *  `ExecStart`: Ruta completa al binario que se debe ejecutar.
    *  `Restart`: Política de reinicio (ej: `on-failure`) .
* **[Install]**: Define cómo se debe habilitar la unidad.
    *  `WantedBy`: Define en qué target se debe incluir (ej: `multi-user.target`).
