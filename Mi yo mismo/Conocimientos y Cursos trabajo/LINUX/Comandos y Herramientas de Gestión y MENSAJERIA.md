##  Comandos y Herramientas de Gestión y MENSAJERIA

### dmesg (Mensajes del Kernel)
*  Se usa para revisar mensajes de controladores y funciones cargados al arrancar 15, 16].
* **Opciones principales:**
    *  `-T`: Muestra marcas de tiempo claramente 18].
    *  `-k`: Solo mensajes del kernel 19].
    *  `-l`: Filtra por niveles de aviso (warn, err, etc.) 20].
*  Es equivalente a `journalctl -b -k` 22].

### Systemctl (Gestión de Systemd)
*  `get-default`: Indica el target por defecto 32].
*  `start/stop/status/restart [unidad]`: Controla el estado del servicio 34].
*  `enable/disable`: Activa o desactiva una unidad al inicio 37].
*  `list-units`: Lista las unidades cargadas 36].
*  `list-dependencies`: Muestra el árbol de dependencias de una unidad 40].
*  `isolate [unidad].target`: Cambia al target seleccionado 35].

### Journalctl (Logs de Systemd)
*  `journalctl`: Consulta los logs del sistema 43].
*  `-S` (Since) y `-U` (Until): Especifica rangos de tiempo (YYYY-MM-DD, yesterday, etc.) 45, 46].
*  `-u [unit]`: Mensajes de una unidad concreta 47].
*  `-p`: Filtra por tipo (emerg, alert, crit, err, warning, notice, info, debug) 49].
