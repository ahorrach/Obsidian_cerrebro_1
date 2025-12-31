El comando `apt` (Advanced Package Tool) fue diseñado como una interfaz de usuario de alto nivel. Aunque `apt-get` sigue siendo preferible para scripts de automatización por su estabilidad, `apt` es la opción preferida para el día a día222.

## Equivalencias de Comandos

|**Acción**|**Comando Antiguo**|**Comando Moderno (apt)**|
|---|---|---|
|**Actualizar índices**|`apt-get update` 3|`apt update`|
|**Instalar paquete**|`apt-get install` 4|`apt install`|
|**Eliminar paquete**|`apt-get remove` 5|`apt remove`|
|**Actualizar sistema**|`apt-get upgrade` 6|`apt upgrade`|
|**Cambio de versión**|`apt-get dist-upgrade` 7|`apt full-upgrade`|
|**Buscar paquetes**|`apt-cache search` 8|`apt search`|
|**Ver información**|`apt-cache show` 9|`apt show`|

---

## Mejoras de `apt` frente a `apt-get`

1. **Interfaz unificada**: No necesitas saltar entre `apt-get` para instalar y `apt-cache` para buscar información
    
2. **Barra de progreso**: Incluye una barra visual en la parte inferior de la terminal que indica el porcentaje de la operación actual
    
3. **Resumen de cambios**: Al realizar actualizaciones, presenta un resumen más legible de los paquetes que se van a instalar, actualizar o eliminar
    
4. **Limpieza automática**: `apt remove` ahora sugiere a menudo la eliminación de dependencias que ya no son necesarias (comportamiento similar a `autoremove`).
    

---

## Flujo de trabajo recomendado con Repositorios

Para mantener el sistema correctamente actualizado según la configuración de `/etc/apt/sources.list`13:

1. **Sincronizar**: `sudo apt update` (descarga la información de los servidores)14.
    
2. **Revisar**: `apt list --upgradable` (comando exclusivo de `apt` para ver qué se puede actualizar).
    
3. **Ejecutar**: `sudo apt upgrade` (aplica las mejoras de seguridad y versiones)15.