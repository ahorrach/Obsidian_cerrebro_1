## 📌 Introducción

La **gestión de particiones** consiste en crear, modificar, borrar y organizar las divisiones de un disco duro o SSD.  
En Linux, esta tarea se realiza habitualmente desde la **línea de comandos**, especialmente en servidores o entornos sin interfaz gráfica.

Las herramientas más importantes son:

- `fdisk` → particiones MBR (BIOS/Legacy)
- `gdisk` → particiones GPT (UEFI)
- `parted` → herramienta moderna
- `lsblk` → visualización de discos y particiones
- `partprobe` → recarga de la tabla de particiones

---

## 1️⃣ fdisk — Gestión clásica de particiones (MBR)

### ¿Qué es fdisk?
`fdisk` es una herramienta **clásica e interactiva** para gestionar tablas de particiones **MBR (Master Boot Record)**.

✔ Muy usada en sistemas antiguos  
❌ No recomendada para discos mayores de 2 TB

---

### Características principales
- Soporta discos hasta **2 TB**
- Máximo **4 particiones primarias**
- Muy simple y ligera
- No modifica el disco hasta guardar cambios

---

### Uso básico
```bash
sudo fdisk /dev/sda
```

---

### Comandos más usados dentro de fdisk

| Comando | Acción |
|------|------|
| `m` | Muestra ayuda |
| `p` | Muestra la tabla de particiones |
| `n` | Crear nueva partición |
| `d` | Borrar partición |
| `t` | Cambiar tipo de partición |
| `w` | Guardar cambios |
| `q` | Salir sin guardar |

📌 **Resumen**:  
👉 `fdisk` es ideal para **prácticas básicas y discos pequeños**.

---

## 2️⃣ gdisk — Gestión de particiones GPT

### ¿Qué es gdisk?
`gdisk` es la alternativa moderna a `fdisk`, diseñada para trabajar con **GPT (GUID Partition Table)**.

✔ Recomendado para sistemas UEFI  
✔ Soporta discos grandes

---

### Características principales
- Discos de más de **2 TB**
- Hasta **128 particiones**
- Interfaz similar a `fdisk`

---

### Uso básico
```bash
sudo gdisk /dev/sda
```

---

📌 **Resumen**:  
👉 `gdisk` es la opción adecuada para **discos grandes y sistemas UEFI**.

---

## 3️⃣ parted — Herramienta avanzada y moderna

### ¿Qué es parted?
`parted` es una herramienta **potente y flexible**, capaz de trabajar con **MBR y GPT**, tanto en modo interactivo como no interactivo.

---

### Características principales
- Soporta MBR y GPT
- Redimensiona particiones
- Permite automatización

---

### Uso interactivo
```bash
sudo parted /dev/sda
```

---

### Ejemplo no interactivo
```bash
sudo parted /dev/sda mklabel gpt
```

📌 **Resumen**:  
👉 `parted` es la **herramienta más completa**.

---

## 4️⃣ lsblk — Visualización de discos y particiones

### ¿Qué es lsblk?
`lsblk` (*list block devices*) muestra de forma **clara y jerárquica** los discos, particiones y puntos de montaje del sistema.

✔ No modifica nada  
✔ Imprescindible antes de particionar

---

### Uso básico
```bash
lsblk
```

Salida típica:
```text
sda      500G
├─sda1   100G  /
├─sda2   300G  /home
└─sda3   100G  [SWAP]
```

---

### Opciones útiles

- `-f` → muestra sistema de archivos y UUID
```bash
lsblk -f
```

- `-o` → selecciona columnas
```bash
lsblk -o NAME,SIZE,TYPE,MOUNTPOINT
```

📌 **Resumen**:  
👉 `lsblk` se usa **antes y después** de modificar particiones para comprobar el resultado.

---

## 5️⃣ partprobe — Recargar la tabla de particiones

### ¿Qué es partprobe?
`partprobe` informa al kernel de los **cambios realizados en la tabla de particiones**, sin necesidad de reiniciar el sistema.

---

### ¿Cuándo usar partprobe?
- Después de usar `fdisk`, `gdisk` o `parted`
- Cuando el sistema no reconoce una nueva partición

---

### Uso básico
```bash
sudo partprobe
```

O sobre un disco concreto:
```bash
sudo partprobe /dev/sda
```

📌 **Importante**:
- No siempre funciona si la partición está en uso
- En algunos casos será necesario reiniciar

---

## 🧠 Comparativa rápida

| Herramienta | Función | Modifica disco |
|------|------|-------------|
| fdisk | Crear particiones MBR | ✅ |
| gdisk | Crear particiones GPT | ✅ |
| parted | Gestión avanzada | ✅ |
| lsblk | Ver discos y particiones | ❌ |
| partprobe | Recargar tabla | ❌ |

---

## ✅ Buenas prácticas

- Usar `lsblk` **antes** de tocar discos
- Verificar siempre el dispositivo (`/dev/sda`, `/dev/sdb`)
- Hacer copia de seguridad
- Usar `partprobe` tras cambios
- En producción, preferir `gdisk` o `parted`

---

## 📌 Flujo típico de trabajo

1. `lsblk` → identificar disco
2. `fdisk` / `gdisk` / `parted` → crear partición
3. `partprobe` → recargar tabla
4. `mkfs` → crear sistema de archivos
5. `mount` → montar
6. `df -h` → verificar
