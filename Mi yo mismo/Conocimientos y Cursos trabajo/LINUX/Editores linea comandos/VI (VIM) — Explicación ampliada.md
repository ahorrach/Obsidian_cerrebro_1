## ¿Qué es _vi_?

_vi_ es el editor de texto clásico de Unix. Está disponible en prácticamente todas las distribuciones Linux y sistemas Unix, incluso en modos de recuperación. Su versión moderna, **Vim** (_Vi IMproved_), añade mejoras como resaltado de sintaxis, autocompletado, macros avanzadas y plugins.

## Filosofía de _vi_

- Editor **modal**: diferentes modos para escribir, navegar o ejecutar comandos.
    
- Extremadamente **rápido** y eficiente.
    
- Funciona sin ratón.
    
- Ideal para administradores de sistemas y usuarios avanzados.
    

## Modos de VI

### 1. Modo Comando (Normal Mode)

Es el modo por defecto. Permite navegar, borrar, copiar, pegar y ejecutar acciones.

- Se accede con **ESC**.
    

### 2. Modo Insertar (Insert Mode)

Permite escribir texto.

- `i` → insertar antes del cursor
    
- `a` → insertar después
    
- `o` → nueva línea debajo
    
- `O` → nueva línea encima
    
- Salir: **ESC**
    

### 3. Modo Ex (Command-Line Mode)

Se accede con `:` y permite ejecutar comandos como guardar, salir o buscar.

- `:w` guardar
    
- `:q` salir
    
- `:wq` guardar y salir
    
- `:q!` salir sin guardar
    

## Navegación esencial

- `h` izquierda
    
- `j` abajo
    
- `k` arriba
    
- `l` derecha
    
- `w` siguiente palabra
    
- `b` palabra anterior
    
- `0` inicio de línea
    
- `$` final de línea
    
- `gg` inicio del archivo
    
- `G` final del archivo
    

## Edición básica

- `dd` borrar línea
    
- `yy` copiar línea
    
- `p` pegar
    
- `u` deshacer
    
- `Ctrl+r` rehacer
    

## Búsqueda

- `/texto` buscar hacia abajo
    
- `?texto` buscar hacia arriba
    
- `n` siguiente coincidencia
    
- `N` anterior