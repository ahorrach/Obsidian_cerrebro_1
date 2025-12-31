
La virtualización permite la abstracción de los recursos físicos de una computadora para crear entornos de ejecución independientes.

## 1. Virtualización de Máquinas Virtuales (VM)

La virtualización tradicional utiliza una capa intermedia para gestionar los recursos físicos.

- **Hypervisor o VMM (Virtual Machine Monitor)**: Es la capa que se sitúa entre el hardware físico y los sistemas operativos de las máquinas virtuales. Su función es dividir los recursos en uno o más entornos de ejecución.
    
- **Componentes**: Involucra el hardware físico, el Hypervisor y las máquinas virtuales (que pueden ejecutar distintos S.O. como Windows, Linux o Solaris).
    
- **Clonación y Plantillas**: Las máquinas virtuales pueden clonarse para usarse como plantillas con configuraciones específicas.
    
    - **Importante**: Al clonar, se deben asegurar identificadores únicos en el sistema, como la **dirección MAC** de las tarjetas de red y el **ID del sistema** (como el `dbus-id`).
        
- **Ejemplos de Software**: VirtualBox, VMware, Xen y Qemu.
    

## 2. Contenedores de Linux

Los contenedores ofrecen una alternativa más ligera a la virtualización completa.

- **Definición**: Permiten empaquetar y aislar aplicaciones junto con todo su entorno de ejecución necesario.
    
- **Funcionamiento**: A diferencia de las VM, los contenedores **no emulan** el hardware ni el kernel del sistema operativo anfitrión.
    
- **Ventajas**:
    
    - Consumen menos recursos de ejecución que las máquinas virtuales.
        
    - Los ficheros ocupan menos espacio en el disco del anfitrión.
        
- **Ejemplos**: Docker y LXC (también se mencionan Xen y Qemu en contextos de virtualización).
    

## 3. Infraestructura como Servicio (IaaS)

Es un modelo donde un proveedor alquila parte de su infraestructura informática.

- **Recursos alquilados**: Servidores, redes y conexión a internet.
    
- **Ventajas**:
    
    - **Pago por uso**: Se paga según las necesidades de hardware del momento, lo que permite un escalado fácil.
        
    - **Ahorro**: Evita el coste de compra y mantenimiento de hardware propio.
        
    - **Flexibilidad**: Al estar virtualizado, facilita la instalación, duplicado y movilidad de sistemas operativos.
        
- **Ejemplos comerciales**: Amazon AWS y Microsoft Azure.
    
- **Acceso seguro**: La gestión de conexiones a estas instancias se realiza habitualmente mediante **claves SSH** para establecer una conexión segura.
 
![[C04-102_6[01]+-++Virtualizacion.pdf]]

![[C04-102_6[02]+-+Contenedores.pdf]]