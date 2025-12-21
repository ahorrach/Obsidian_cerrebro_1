### MBR (Master Boot Record)
# MBR vs. GPT: Comparativa de Sistemas de Particiones

Este documento detalla las diferencias técnicas entre el Master Boot Record (MBR) y la GUID Partition Table (GPT) basándose en la documentación técnica proporcionada.

---

## 1. Master Boot Record (MBR)
* **Ubicación:** Se encuentra en el primer sector del disco.
* **Tabla de particiones:** Contiene una tabla limitada a 4 particiones.
* **Tipos de partición:** Soporta particiones de tipo primaria, extendida o lógica.
* **Limitación de capacidad:** No es capaz de manejar particiones que superen los 2 TB.

---

## 2. GUID Partition Table (GPT)
* **Compatibilidad:** Es compatible con el sistema MBR.
* **Requisitos de Firmware:** No funciona con BIOS tradicional; requiere obligatoriamente EFI o UEFI.
* **Capacidad de almacenamiento:** Soporta tamaños de disco masivos de hasta 9,4 zettabytes.
* **Gestión de particiones:** Puede gestionar todas las particiones que el Sistema Operativo soporte, siendo lo habitual hasta 128 particiones.
* **Rendimiento:** Ofrece una mejor gestión del proceso de arranque del Sistema Operativo.

---

## 3. Tabla Comparativa Resumen

| Característica | MBR | GPT |
| :--- | :--- | :--- |
| **Ubicación** | [cite_start]Primer sector del disco [cite: 3] | [cite_start]Distribuido (compatible con MBR) [cite: 9] |
| **Límite de Particiones** | [cite_start]4 particiones [cite: 4] | [cite_start]Habitualmente 128 [cite: 11] |
| **Tamaño Máximo** | [cite_start]2 TB [cite: 6] | [cite_start]9,4 Zettabytes [cite: 11] |
| **Firmware Necesario** | [cite_start]BIOS [cite: 10] | [cite_start]EFI o UEFI [cite: 10] |
![[C04-101_2[04]+-+MBR+y+GPT.pdf]]