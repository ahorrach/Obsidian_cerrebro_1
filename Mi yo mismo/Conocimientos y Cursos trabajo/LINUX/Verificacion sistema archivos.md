#  Administración del sistema de archivos en Linux
_Formato Markdown para Obsidian_

---

## 1️⃣ Comprobación del sistema de archivos (fsck)

### ¿Qué es fsck?
`fsck` (File System Consistency Check) es una herramienta que **verifica y repara la integridad del sistema de archivos** en Linux.  
Se utiliza tras apagados incorrectos, errores de disco o como mantenimiento preventivo.

⚠️ **Nunca ejecutar fsck sobre un sistema de archivos montado**.

---

### Tipos de fsck según el sistema de archivos

- **e2fsck** → EXT2 / EXT3 / EXT4  
- **dosfsck** → FAT / FAT32  
- **reiserfsck** → ReiserFS  
- **xfs_repair** → XFS

Ejemplo:
```bash
sudo fsck /dev/sda1
```

---

### Opciones importantes de fsck

- `-A` → Verifica todos los sistemas de archivos de `/etc/fstab`
- `-C` → Muestra progreso
- `-V` → Modo detallado
- `-N` → Simulación (no realiza cambios)
- `-f` → Fuerza la comprobación
- `-p` → Repara automáticamente

Ejemplo seguro:
```bash
sudo fsck -N /dev/sdb1
```

Ejemplo de reparación:
```bash
sudo fsck -fp /dev/sdb1
```

---

### Herramientas para sistemas EXT

#### dumpe2fs
Muestra información técnica del sistema de archivos:
```bash
sudo dumpe2fs -h /dev/sda1
```

#### tune2fs
Permite modificar parámetros del sistema de archivos:
- `-c` → Nº de montajes antes de fsck
- `-i` → Tiempo máximo entre comprobaciones
- `-m` → Espacio reservado para root
- `-L` → Etiqueta

Ejemplo:
```bash
sudo tune2fs -i 1m /dev/sdb1
```

---

### Sistemas de archivos XFS

- `xfs_repair` → Reparación
- `xfs_db` → Depuración
- `xfs_fsr` → Desfragmentación

Ejemplo:
```bash
sudo xfs_repair /dev/sdc1
```

---

