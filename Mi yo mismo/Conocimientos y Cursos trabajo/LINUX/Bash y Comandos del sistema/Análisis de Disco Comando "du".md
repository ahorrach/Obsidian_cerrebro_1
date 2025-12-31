
El comando `du` (_Disk Usage_) se utiliza para estimar el uso de espacio de archivos y directorios. Es fundamental para identificar qué carpetas están ocupando más espacio en el sistema.

### Opciones comunes

- **`-s`**: (_Summary_) Muestra solo el total de cada argumento.
    
- **`-h`**: (_Human-readable_) Muestra los tamaños en formato legible (K, M, G).
    

### Ejemplos avanzados

- **Ver el tamaño de todos los directorios en la raíz:** `du -sh /* 2> /dev/null` _(Nota: `2> /dev/null` oculta los errores de permisos denegados en carpetas del sistema)._
    
- **Encontrar el directorio más grande:** `du -sh /* 2> /dev/null | sort -h | tail -n1`
    
    - Explicación: `sort -h` ordena por tamaño real (entendiendo G > M) y `tail -n1` muestra solo la última línea (la más pesada).
        