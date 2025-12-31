## Comandos de Gestión de Módulos

A continuación se detallan las herramientas de línea de comandos para administrar estos componentes:

### 1. Consulta e Información

|**Comando**|**Descripción**|
|---|---|
|`lsmod`|Muestra la lista de todos los módulos cargados actualmente en el sistema5.|
|`modinfo`|Proporciona información detallada sobre un módulo específico6.|

### 2. Gestión Manual (Baja Nivel)

- **`insmod`**: Carga un fichero `.ko` específico en el sistema7.
    
- **`rmmod`**: Quita un módulo que esté cargado en el sistema8.
    
    - `-w`: Espera a que el módulo deje de utilizarse antes de removerlo9.
        
    - `-f`: Fuerza el borrado del módulo10.
        

### 3. Gestión Inteligente (Alta Nivel)

El comando **`modprobe`** es el estándar moderno ya que permite cargar o borrar módulos resolviendo automáticamente las **dependencias** entre ellos11.

**Opciones comunes de `modprobe`:**

- `-r`: Elimina el módulo del sistema12.
    
- `-f`: Fuerza la carga del módulo incluso si la versión del kernel no coincide con la esperada13.
    
- `-v`: Modo _verbose_; muestra información adicional sobre las acciones que realiza14.
    
- `-n`: Realiza una simulación de la operación (dry run) sin llegar a insertar el módulo realmente15.
    


![[C04-101_1[05]+-+modulos.pdf]]