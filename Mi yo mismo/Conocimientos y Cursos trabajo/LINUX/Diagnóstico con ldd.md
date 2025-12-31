## Sintaxis y Uso

La sintaxis básica es: `ldd [opciones] /ruta/al/programa`

### Ejemplos Prácticos

#### 1. Ver librerías de un comando común

Si quieres saber de qué librerías depende el comando `ls`:

Bash

```
ldd /bin/ls
```

_Salida típica:_

Plaintext

```
linux-vdso.so.1 (0x00007ffce67e3000)
libselinux.so.1 => /lib/x86_64-linux-gnu/libselinux.so.1 (0x00007f3a1b2e0000)
libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f3a1b000000)
/lib64/ld-linux-x86-64.so.2 (0x00007f3a1b33b000)
```

#### 2. Identificar librerías faltantes ("not found")

Si un programa falla al arrancar, `ldd` te mostrará si falta alguna dependencia:

Plaintext

```
libcustom.so.1 => not found
```

> [!IMPORTANT] Si aparece "not found", el sistema no encuentra la librería en las rutas estándar ni en `/etc/ld.so.conf`. Podrías necesitar usar `ldconfig` tras instalarla o definir `LD_LIBRARY_PATH`.

#### 3. Ver todas las dependencias (Modo detallado)

Para obtener un informe completo, incluyendo versiones y relaciones:

Bash

```
ldd -v /bin/bash
```

Esto es útil para depurar conflictos entre versiones de archivos `.so`.

#### 4. Comprobar funciones no resueltas

Si sospechas que la librería existe pero es incompatible o está corrupta:

Bash

```
ldd -r /ruta/al/binario
```

_(Realiza reubicaciones de datos y funciones para encontrar símbolos faltantes)._

---

## Relación con otros elementos del sistema

- **`ldconfig`**: Si instalas una nueva librería en `/usr/local/lib`, `ldd` no la verá hasta que ejecutes `ldconfig` para actualizar la caché del sistema.
    
- **`.so`**: `ldd` siempre buscará estos archivos ("Shared Objects"), que suelen estar enlazados simbólicamente entre versiones.