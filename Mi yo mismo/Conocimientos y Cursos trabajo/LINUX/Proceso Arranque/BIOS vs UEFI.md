
## BIOS (Basic Input/Output System)

La **BIOS** es un firmware almacenado en memoria ROM o PROM cuya función principal es iniciar el sistema y permitir la configuración básica del hardware.

### Funciones principales
- Inicializa los componentes esenciales del sistema.
- Permite el arranque del sistema operativo.
- Proporciona una interfaz básica de configuración del hardware.

### Partes fundamentales
- **Setup**
  - Permite configurar opciones del sistema (fecha, hora, orden de arranque, dispositivos, etc.).
  - Se accede al encender el equipo pulsando una tecla específica, normalmente **Supr**.

- **POST (Power-On Self Test)**
  - Comprueba que los componentes principales del sistema funcionen correctamente antes del arranque.

---

## UEFI (Unified Extensible Firmware Interface)

**UEFI** es la evolución moderna de la BIOS tradicional, diseñada para superar sus limitaciones y ofrecer mayor flexibilidad y seguridad.

### Características principales
- Compatibilidad y emulación de la BIOS tradicional.
- Soporte para la **tabla de particiones GUID (GPT)**.
- Capacidad para arrancar desde discos de gran tamaño.
- Entorno más amigable, flexible y gráfico.
- Posibilidad de incluir capacidades de red.
- Diseño modular.
- Soporte para **Secure Boot (arranque seguro)**.

---

## Diferencias clave entre BIOS y UEFI

| BIOS | UEFI |
|------|------|
| Tecnología antigua | Tecnología moderna |
| Limitada a MBR (≤ 2 TB) | Soporta GPT (> 2 TB) |
| Interfaz básica | Interfaz gráfica avanzada |
| Sin arranque seguro | Incluye Secure Boot |
![[C04-101_2[01]+-+BIOS.pdf]]

![[C04-101_2[02]+-+UEFI.pdf]]