
Lista el contenido de un directorio. Es el comando más usado para navegar.

- **Opciones clave**:
    
    - `ls -l`: Formato largo. Muestra permisos, propietario, grupo, tamaño y fecha.
        
    - `ls -h`: (Human-readable) Convierte los tamaños a KB, MB o GB.
        
    - `ls -a`: Muestra archivos ocultos (los que empiezan por punto, ej. `.bashrc`).
        
    - `ls -S`: Ordena los archivos por **tamaño** (mayor a menor).
        
    - `ls -t`: Ordena por **fecha de modificación** (más reciente primero).
        
    - `ls -r`: Invierte el orden de cualquier clasificación.
        
- **Ejemplos Pro**:
    
    - `ls -lhS`: Ver archivos grandes detallados.
        
    - `ls -ltr`: Ver qué archivos se han modificado recientemente al final de la lista.
        

### 5. `rm` (Remove)

Borra archivos o directorios. **Cuidado:** No hay "papelera de reciclaje" en la terminal; lo que borras desaparece.

- **Opciones clave**:
    
    - `rm -r`: (Recursive) Borra directorios y todo su contenido.
        
    - `rm -f`: (Force) Borra sin preguntar y omite archivos que no existen.
        
    - `rm -i`: Modo interactivo; te pregunta antes de borrar cada archivo (seguridad).
        
- **Peligro**: `sudo rm -rf /` intentaría borrar todo el sistema.
    

---

# 🔑 Gestión de Privilegios: `sudo` y `su`

Para realizar tareas administrativas (instalar paquetes, tocar archivos de `/etc`), necesitas privilegios de **root** (superusuario).

### 1. `su` (Substitute User)

Te permite convertirte en otro usuario (por defecto, el superusuario `root`).

- **`su -`**: Cambia a root cargando también su entorno de variables (como su propio `$PATH`). Pide la contraseña del usuario **root**.
    
- **`su [usuario]`**: Te cambia a la sesión de otro usuario específico.
    

### 2. `sudo` (SuperUser Do)

Permite a un usuario normal ejecutar un comando con privilegios de root.

- **Funcionamiento**: A diferencia de `su`, pide **tu propia contraseña**, no la de root.
    
- **`sudo -i`**: Te da una shell persistente como root (similar a `su -` pero con tu clave).
    
- **`sudo !!`**: Ejecuta el comando anterior pero con sudo (muy útil cuando olvidas ponerlo).
    

---

### Tabla de Seguridad: ¿Cuál usar?

|**Comando**|**Contraseña requerida**|**Uso recomendado**|
|---|---|---|
|**`sudo`**|La tuya (del usuario actual)|**Óptimo**: Ejecutar una sola tarea y volver a ser usuario normal.|
|**`su -`**|La de **root**|Solo si necesitas hacer muchas tareas de administración seguidas.|

