El comando `dpkg` permite administrar paquetes sin necesidad de repositorios.

### Comandos de Instalación y Borrado

- **`-i`**: Instala un paquete. Requiere la ruta completa al archivo `.deb`.
    
    - _Ejemplo:_ `dpkg -i htop_2.0.2-1_amd64.deb`.
        
- **`-r`**: Borra un paquete pero **mantiene** los ficheros de configuración.
    
    - _Ejemplo:_ `dpkg -r htop`.
        
- **`-P`**: Borra el paquete de forma completa, **incluyendo** los ficheros de configuración.
    
    - _Ejemplo:_ `dpkg -P htop`.
        

### Comandos de Consulta

- **`-s`**: Muestra el estado e información de un paquete ya **instalado**.
    
- **`-I`**: Muestra información de un **archivo .deb** (sin necesidad de estar instalado).
    
- **`-l`**: Lista todos los paquetes instalados que coincidan con un patrón.
    
    - _Ejemplo:_ `dpkg -l apache*`.
        
- **`-L`**: Muestra todos los ficheros que han sido instalados por un paquete específico.
    
- **`-S`**: Busca qué paquete contiene un fichero determinado.
    
    - _Ejemplo:_ `dpkg -S mount*`.
        

### Reconfiguración

- **`dpkg-reconfigure`**: Se utiliza para volver a configurar un paquete que ya se encuentra instalado en el sistema.
    
    - _Ejemplo:_ `dpkg-reconfigure nslcd`.