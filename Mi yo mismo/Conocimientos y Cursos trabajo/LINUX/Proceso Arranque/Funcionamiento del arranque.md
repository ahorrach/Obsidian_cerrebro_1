El proceso de arranque es el conjunto de pasos que se ejecutan desde que se enciende el ordenador hasta que el sistema operativo comienza a funcionar.

### Pasos del arranque
- Al encender el PC se ejecuta el firmware de la **BIOS** o **UEFI**.
- El **POST (Power-On Self Test)** comprueba que el hardware básico funcione correctamente.
- El sistema busca un **cargador de arranque** siguiendo el orden establecido en la secuencia de arranque configurada en el *setup*.
- Si el sistema utiliza **BIOS**:
  - Se lee el primer sector de la unidad de almacenamiento, llamado **MBR (Master Boot Record)**.
  - En el MBR se encuentra el código necesario para localizar y ejecutar el gestor de arranque.
- Si el sistema utiliza **UEFI**:
  - Se ejecuta directamente el gestor de arranque almacenado en una **partición especial llamada ESP (EFI System Partition)**.

Detalle del proceso
- [[BIOS vs UEFI]]
- [[MBR (ante UEFI) vs GPT (desde uefi)]]
- [[ Gestores de arranque (LILO, GRUB, GRUB2)]]