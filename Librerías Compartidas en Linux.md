
Las librerías compartidas son ficheros que ponen a disposición del sistema operaciones comunes (acceso a disco, interfaces gráficas, formularios, etc.). De este modo, el software no necesita incluir el código de estas funciones en cada ejecutable, sino que las "comparte".

## Características Técnicas

- **Extensión**: Los archivos de librería utilizan la extensión `.so` (_shared object_).
    
- **Versiones**: Los nombres de archivo suelen indicar la versión de la librería.
    
- **Enlaces**: Es habitual la creación de enlaces simbólicos entre versiones que son compatibles entre sí.
    

---

## Ubicación y Búsqueda

El sistema busca estas librerías siguiendo un orden de preferencia específico:

1. **Variable `LD_LIBRARY_PATH`**: Contiene directorios definidos por el usuario. Se utiliza para cambios temporales o librerías muy específicas y tiene la mayor preferencia.
    
2. **Directorios estándar**: `/lib/` y `/usr/lib/` (o sus equivalentes en sistemas de 64 bits).
    
3. **Configuración del sistema**: Directorios indicados en el archivo `/etc/ld.so.conf`.
    

---

## Configuración y Herramientas

### El archivo `/etc/ld.so.conf`

Este archivo gestiona los directorios de librerías de forma modular:

- Suele utilizar la directiva `include` para importar todos los archivos con extensión `.conf` ubicados en `/etc/ld.so.conf.d/`.
    
- **Actualización**: Si se modifica cualquier archivo de configuración, se debe ejecutar el comando `ldconfig` para que los cambios surtan efecto.
    
- **Caché**: El comando `ldconfig` genera una caché de los directorios y ficheros compartidos para acelerar el acceso.
    

### [[Diagnóstico con ldd]]

- El comando `ldd` se utiliza para mostrar qué librerías específicas necesita un programa determinado del sistema para funcionar.

