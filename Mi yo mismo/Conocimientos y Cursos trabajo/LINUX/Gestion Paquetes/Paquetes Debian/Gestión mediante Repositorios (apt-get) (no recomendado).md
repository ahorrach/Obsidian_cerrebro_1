`apt-get` utiliza servidores denominados **repositorios** para localizar e instalar paquetes `.deb` de forma automática.

### Configuración: `sources.list`

Los repositorios se configuran en el archivo `/etc/apt/sources.list`. Cada línea representa un repositorio con el siguiente formato: `deb http://deb.debian.org/debian/ buster main contrib`

1. **Tipo**: `deb` para paquetes binarios o `deb-src` para códigos fuente.
    
2. **URL**: Dirección del servidor (ej. `http://deb.debian.org/`).
    
3. **Distribución**: La rama del sistema (ej. `debian/`).
    
4. **Versión**: Palabra clave de la versión (ej. `buster`).
    
5. **Secciones**: Organización de los paquetes (ej. Debian usa `main`, `contrib` y `non-free`).
    

### Acciones de `apt-get`

- **`update`**: Actualiza la información local sobre los paquetes disponibles en los repositorios.
    
- **`install`**: Instala uno o varios paquetes nuevos.
    
- **`remove`**: Desinstala paquetes.
    
- **`upgrade`**: Actualiza todos los paquetes instalados a sus versiones más recientes (dentro de la misma versión de la distribución).
    
- **`dist-upgrade`**: Actualiza el sistema a la última versión configurada en los repositorios, gestionando cambios de dependencias.
    
- **`clean`**: Borra los archivos `.deb` descargados y almacenados en el disco para liberar espacio.
    

---

## 3. Consultas con `apt-cache`

Esta herramienta trabaja con la base de datos interna de la información de paquetes.

- **`search`**: Busca un patrón o término en los nombres o descripciones de los paquetes.
    
- **`show`**: Muestra información detallada de un paquete específico.