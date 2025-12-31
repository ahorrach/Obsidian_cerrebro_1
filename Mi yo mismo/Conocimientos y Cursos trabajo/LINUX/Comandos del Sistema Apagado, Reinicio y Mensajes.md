Desde la terminal de Linux, se pueden enviar comandos para controlar el estado del sistema y la comunicación entre terminales1.

## 1. Comandos de Control de Energía

### Comandos Principales

- **`shutdown`**: Apaga el sistema de forma planificada2.
    
- **`halt`**: Cierra el sistema 3sin enviar la señal ACPI de corte de alimentación eléctrica4.
    
- **`poweroff`**: Apaga el sistema enviando la señal ACPI5.
    
- **`reboot`**: Reinicia el sistema6.
    

### Tabla de Equivalencias

Dependiendo del comando base utilizado, se pueden lograr los mismos resultados con diferentes parámetros7:

|**Acción**|**Comando Directo**|**Con shutdown**|**Con otros comandos**|
|---|---|---|---|
|**Reiniciar**|`reboot` 8|`shutdown -r` 9|`halt --reboot` 10|
|**Cerrar sistema**|`halt` 11|`shutdown -H` 12|`reboot --halt` 13|
|**Apagar**|`poweroff` 14|`shutdown -P` 15|`halt -p` 16|

---

## 2. Uso Avanzado de `shutdown`

El comando sigue la sintaxis: `shutdown [opción] TIEMPO [mensaje]`17.

Opciones 18

- **`-c`**: Cancela una orden de apagado que ya ha sido programada19.
    
- **`-k`**: Envía los mensajes de advertencia a los usuarios pero **no** llega a apagar el sistema20.
    

Especificación del Tiempo 21

- **`HH:MM`**: Formato de hora y minutos específicos.
    
- **`+M`**: Cantidad de minutos que faltan para el apagado (ej. `+10`).
    
- **`now`**: Ejecuta la acción de forma inmediata.
    

---

## 3. Gestión de Mensajes

- **`wall`**: Envía un mensaje de texto a todos los terminales de los usuarios conectados22.
    
- **`mesg`**: Gestiona si el terminal acepta o no la recepción de mensajes23.
    
    - **`y`**: Permite la recepción (sí)24.
        
    - **`n`**: Bloquea la recepción (no)25.
        
    - **Sin parámetros**: Al ejecutarlo solo, consulta el estado actual del valor26.
        
    - **Con parámetros**: Al pasarle `y` o `n`, modifica el estado actual27.
    
 ![[C04-101_3[01]+-+apagar,+reiniciar+y+mensajes.pdf]]