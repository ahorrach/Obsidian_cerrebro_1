

#bash #linux #cli #atajos

--------------------------------
AUTOCOMPLETADO (TAB)
--------------------------------
TAB        -> Autocompleta comandos, archivos y directorios
TAB TAB    -> Muestra todas las opciones
./scr<TAB> -> Autocompleta ejecutables

--------------------------------
HISTORIAL DE COMANDOS
--------------------------------
↑ / Ctrl+P -> Comando anterior
↓ / Ctrl+N -> Comando siguiente
Ctrl+R    -> Buscar hacia atrás en el historial
Ctrl+G    -> Cancelar búsqueda

history   -> Lista historial numerado
!!        -> Último comando
!123      -> Ejecuta comando nº 123
!ls       -> Último comando que empieza por "ls"
!?ssh?    -> Último comando que contiene "ssh"

--------------------------------
MOVIMIENTO DEL CURSOR
--------------------------------
Ctrl+A -> Inicio de línea
Ctrl+E -> Final de línea
Alt+B  -> Palabra atrás
Alt+F  -> Palabra adelante
Ctrl+B -> Carácter atrás
Ctrl+F -> Carácter adelante

--------------------------------
BORRAR TEXTO
--------------------------------
Ctrl+U -> Borra hasta el inicio
Ctrl+K -> Borra hasta el final
Ctrl+W -> Borra palabra anterior
Alt+D  -> Borra palabra siguiente
Ctrl+H -> Backspace

--------------------------------
COPIAR / PEGAR (KILL & YANK)
--------------------------------
Ctrl+Y -> Pegar lo borrado
Alt+Y  -> Rotar entre cortes

--------------------------------
CONTROL DE PROCESOS
--------------------------------
Ctrl+C -> Mata proceso
Ctrl+Z -> Suspende proceso
fg     -> Reanudar en primer plano
bg     -> Reanudar en segundo plano
jobs   -> Ver procesos

--------------------------------
PANTALLA / TERMINAL
--------------------------------
Ctrl+L -> Limpiar pantalla
reset  -> Resetear terminal
exit   -> Salir de bash

--------------------------------
EXPANSIONES ÚTILES
--------------------------------
!!   -> Último comando
!$   -> Último argumento
!*   -> Todos los argumentos
^a^b -> Reemplaza a por b en el último comando

Ejemplo:
mkdir carpeta
cd !$

--------------------------------
ATAJOS AVANZADOS
--------------------------------
Ctrl+X Ctrl+E -> Editar comando en $EDITOR
Alt+.        -> Último argumento
Ctrl+D       -> EOF / salir

--------------------------------
MODOS DE EDICIÓN
--------------------------------
set -o emacs -> Modo por defecto
set -o vi    -> Modo vi
