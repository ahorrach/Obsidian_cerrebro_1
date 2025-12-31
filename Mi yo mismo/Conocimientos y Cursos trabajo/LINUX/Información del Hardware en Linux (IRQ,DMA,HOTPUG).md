
Linux proporciona múltiples formas de obtener información detallada del hardware del sistema. Gran parte de esta información se expone a través del sistema de archivos virtual **/proc**, que no contiene archivos reales en disco, sino datos generados dinámicamente por el kernel.

---

## IRQ (Interrupt Request)

Las **IRQ** son señales enviadas por los dispositivos hardware a la CPU para solicitar atención. Por ejemplo, cuando se pulsa una tecla o se mueve el ratón, el dispositivo genera una interrupción.

- Permiten que la CPU atienda eventos hardware de forma eficiente.
    
- Cada dispositivo suele tener asignado un número de IRQ.
    
- En sistemas modernos, muchas IRQ pueden compartirse.
    

📂 **Archivo de información:**

```
/proc/interrupts
```

Este archivo muestra las interrupciones activas y qué dispositivos las están utilizando.

---

## DMA (Direct Memory Access)

El **DMA** permite que ciertos dispositivos accedan directamente a la memoria RAM sin intervención constante de la CPU.

### Ventajas del DMA:

- Reduce la carga de trabajo de la CPU.
    
- Mejora el rendimiento en operaciones de entrada/salida intensivas.
    

📂 **Archivo de información:**

```
/proc/dma
```

Aquí se listan los canales DMA asignados a los dispositivos.

---

## Direcciones de Entrada/Salida (E/S)

Las **direcciones E/S** son rangos de memoria reservados para que los dispositivos hardware se comuniquen con la CPU.

- Cada dispositivo tiene asignado un rango específico.
    
- Evitan conflictos entre dispositivos.
    

📂 **Archivo de información:**

```
/proc/ioports
```

Muestra los rangos de puertos de E/S utilizados por cada dispositivo.

---

## Coldplug y Hotplug

Linux distingue entre dispositivos según el momento en que pueden conectarse:

### 🔌 Coldplug

- Deben conectarse cuando el equipo está apagado.
    
- Ejemplo: discos duros internos tradicionales.
    

### 🔥 Hotplug

- Pueden conectarse con el sistema en funcionamiento.
    
- Linux detecta y configura el dispositivo automáticamente.
    
- Ejemplos: USB, discos externos, ratones, teclados.
    

El sistema **udev** se encarga de gestionar estos eventos en sistemas Linux modernos.

---

## Resumen

Linux ofrece un control y visibilidad muy detallados del hardware del sistema mediante interfaces estándar del kernel. Comprender conceptos como IRQ, DMA y E/S es fundamental para administración de sistemas, diagnóstico de problemas y optimización del rendimiento.

---

![[C04-101_1[01]+-+intro (1).pdf]]