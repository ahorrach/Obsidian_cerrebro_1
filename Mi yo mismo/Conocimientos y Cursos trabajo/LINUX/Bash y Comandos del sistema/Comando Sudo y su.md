Gestión de Privilegios: `sudo` y `su`

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

