El formato RPM (_Red Hat Package Manager_) es el estándar utilizado por distribuciones como Red Hat, Fedora, CentOS y SUSE.

## 1. Gestión Local con `rpm`

El comando `rpm` se utiliza para administrar paquetes de forma local.

### Instalación y Actualización

- **`-i`**: Instala un paquete. Requiere la ruta completa del archivo `.rpm`.
    
- **`-U`**: Instala un paquete si no existe o lo actualiza si ya está instalado.
    
- **`-F`**: Actualiza un paquete **solo** si ya se encuentra instalado en el sistema.
    
- **Opciones de visualización** (combinables con las anteriores):
    
    - **`h`**: Muestra marcas de hash para indicar el progreso de la operación.
        
    - **`v`**: Modo _verbose_; muestra detalles del progreso para cada paquete.
        

### Eliminación y Verificación

- **`-e`**: Elimina un paquete del sistema.
    
- **`-V`**: Verifica un paquete, comparando la información instalada con la del paquete original (cambios, integridad, etc.).
    

### Consultas (`-q`)

El parámetro `-q` permite realizar diversas consultas:

- **`-qa`**: Lista todos los paquetes instalados en el sistema11.
    
- **`-qi`**: Muestra información detallada de un paquete instalado
    
- **`-ql`**: Lista los ficheros instalados por un paquete específico
    
- **`-qf`**: Muestra a qué paquete pertenece un fichero especificado
    
- **`-qp`**: Muestra información sobre un archivo `.rpm` que **no** está instalado
    

---

## 2. Gestión con Repositorios (`yum`)

`yum` utiliza repositorios para gestionar dependencias de forma automática

### Configuración

Los repositorios se configuran en archivos dentro del directorio `/etc/yum.repos.d/`

- **Estructura de un archivo `.repo`**:
    
    - **`[base]`**: Nombre del repositorio18181818.
        
    - **`mirrorlist`**: URL con la lista de servidores; `yum` seleccionará el más rápido
        
    - **`gpgcheck=1`**: Activa la comprobación de firmas GPG para mayor seguridad
        
    - **`gpgkey`**: Ruta al archivo de la llave GPG.
        
- **Variables automáticas**: `yum` utiliza `$basearch` (arquitectura) y `$releasever` (versión) para autocompletar rutas.
    

### Comandos Principales

- **`install` / `remove`**: Instala o desinstala uno o varios paquetes23.
    
- **`update`**: Actualiza paquetes específicos24.
    
- **`check-update`**: Comprueba qué paquetes instalados tienen actualizaciones disponibles.
    
- **`upgrade`**: Actualiza el sistema a la última versión configurada.
    
- **`search` / `info`**: Busca paquetes por patrón o muestra su información.
    
- **`list`**: Lista paquetes (opciones: `all`, `available`, `updates`, `installed`, etc.).
    
- **`repolist`**: Muestra los repositorios que están activos actualmente.
    
- **`clean`**: Limpia el directorio de caché para liberar espacio.
    

---

## 3. Otras Herramientas y Evolución

### `dnf` y `zypper`

- **`dnf`**: Evolución de `yum` creada por Fedora. Es más eficiente y cuenta con una programación más moderna31.
    
- **`zypper`**: Es el gestor de paquetes específico de la distribución **SUSE**
    

### Extracción manual: `rpm2cpio`

Permite extraer el contenido de un paquete sin instalarlo33333333:

1. Convierte el .rpm a formato .cpio:
    
    `rpm2cpio archivo.rpm > archivo.cpio
    
2. Extrae los archivos (se recomienda hacerlo en un directorio vacío):
    
    `cpio -i --make-directories < archivo.cpio