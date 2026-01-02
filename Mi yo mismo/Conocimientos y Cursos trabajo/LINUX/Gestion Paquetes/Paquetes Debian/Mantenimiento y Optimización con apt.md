Cuando instalamos y desinstalamos software, el sistema puede acumular archivos innecesarios. El comando `apt` ofrece herramientas específicas para mantener el sistema limpio.

## 1. Limpieza de Paquetes Huérfanos

- **`apt autoremove`**: Este comando elimina automáticamente los paquetes que se instalaron como dependencias para satisfacer las necesidades de otro programa y que ya no son requeridos porque el programa principal fue eliminado.
    
- **`apt purge`**: Similar a `dpkg -P`1, elimina no solo el paquete sino también sus archivos de configuración del sistema.
    

## 2. Gestión de la Caché

Cada vez que descargas un programa, el archivo `.deb` se guarda en el disco.

- **`apt clean`**: Borra todos los archivos `.deb` almacenados en la caché de `/var/cache/apt/archives/`2. Es ideal para liberar espacio rápidamente.
    
- **`apt autoclean`**: A diferencia de `clean`, solo borra los archivos `.deb` que ya no pueden descargarse (versiones antiguas que ya no están en los repositorios).
    

---

## Tabla Comparativa: dpkg vs. apt

|**Característica**|**dpkg**|**apt / apt-get**|
|---|---|---|
|**Fuente**|Archivos locales `.deb` 3|Repositorios remotos 4|
|**Dependencias**|No las resuelve (da error)|Las resuelve e instala automáticamente 5|
|**Uso principal**|Instalación manual y consultas 6666|Gestión general del sistema 7777|
|**Configuración**|No requiere archivos extra|Usa `/etc/apt/sources.list` 8|

---

## Ejemplo de flujo de limpieza completa

Si quieres dejar el sistema impecable tras desinstalar un programa pesado, puedes usar:

Bash

```
sudo apt remove [paquete]      # Quita el programa [cite: 97]
sudo apt autoremove            # Quita dependencias sobrantes
sudo apt purge                 # (Opcional) Borra configuraciones
sudo apt clean                 # Borra instaladores descargados 

se pueden ejecutar todos juntos con este comando:

sudo apt autoremove && sudo apt purge && sudo apt clean
```