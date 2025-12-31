## Introducción

Linux proporciona herramientas en línea de comandos para obtener información detallada del hardware conectado al sistema. Dos de las más importantes para el diagnóstico y la administración del sistema son **lspci** y **lsusb**, que permiten inspeccionar dispositivos conectados a los buses **PCI** y **USB** respectivamente.

---

## lspci

El comando **lspci** muestra información sobre los **buses PCI** y los dispositivos conectados a ellos.

📌 Se utiliza principalmente para identificar:

- Tarjetas de red
    
- Tarjetas gráficas
    
- Controladoras de disco
    
- Dispositivos internos del sistema
    

### Uso básico

```
lspci
```

Muestra una lista resumida de todos los dispositivos PCI detectados.

### Opciones más utilizadas

#### `-v` (verbose)

Amplía la información mostrada:

```
lspci -v
```

#### `-vv` (very verbose)

Muestra aún más detalles técnicos:

```
lspci -vv
```

#### `-s` (select)

Muestra información solo del dispositivo seleccionado:

```
lspci -s 00:1f.6
```

### Información mostrada

- Identificador del bus
    
- Fabricante y modelo
    
- Controlador en uso
    
- Recursos asignados (IRQ, direcciones E/S)
    

📌 _lspci obtiene gran parte de su información desde sysfs y la base de datos PCI._

---

## lsusb

El comando **lsusb** muestra información sobre los **buses USB** y los dispositivos conectados.

📌 Se utiliza para identificar:

- Pendrives
    
- Teclados y ratones
    
- Cámaras
    
- Dispositivos USB externos
    

### Uso básico

```
lsusb
```

Muestra una lista de dispositivos USB conectados.

### Opciones más utilizadas

#### `-v` y `-vv`

Amplían el nivel de detalle (igual que en lspci):

```
lsusb -v
lsusb -vv
```

⚠️ _Normalmente requiere permisos de superusuario para mostrar toda la información._

#### `-s` (select)

Muestra información solo del dispositivo seleccionado:

```
lsusb -s 002:003
```

#### `-t` (tree)

Muestra los dispositivos en forma de árbol y la velocidad del puerto USB:

```
lsusb -t
```

### Información mostrada

- Bus USB
    
- ID del dispositivo
    
- Fabricante y modelo
    
- Velocidad de conexión (Low, Full, High, SuperSpeed)
    

---

## Comparación rápida

|Comando|Tipo de bus|Uso principal|
|---|---|---|
|lspci|PCI|Hardware interno|
|lsusb|USB|Hardware externo|

---

## Relación con otros sistemas de Linux

- Ambos comandos usan información del kernel expuesta en **/sys** (sysfs).
    
- Complementan a herramientas como `dmesg`, `udevadm` y `/proc`.
    
- Son fundamentales para diagnóstico de hardware y drivers.
    

---

## Resumen

- **lspci**: inspecciona dispositivos conectados al bus PCI.
    
- **lsusb**: inspecciona dispositivos conectados al bus USB.
    
- Las opciones `-v`, `-vv` y `-s` funcionan de forma similar en ambos comandos.
    
- `lsusb -t` permite visualizar la topología y velocidad USB.
    

---

![[C04-101_1[04]+-+lspci+y+lsusb.pdf]]