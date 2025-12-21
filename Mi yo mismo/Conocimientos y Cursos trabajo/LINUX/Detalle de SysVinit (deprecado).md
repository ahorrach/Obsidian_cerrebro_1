### Detalle de SysVinit
*  Configuración básica en `/etc/inittab` (nivel por defecto y acciones) .
*  El script `rc` ejecuta los ficheros en `/etc/rc.d/` por orden numérico según el nivel de ejecución .
*  Los ficheros son enlaces a `/etc/init.d/`: los que empiezan por **S** ejecutan `start` y los que empiezan por **K** ejecutan `stop` .

| Nivel | Descripción General  118-129]   | En Debian  132-136]                 |
| :---- | :------------------------------ | :---------------------------------- |
| 0     | Apagar el sistema               | Apagar                              |
| 1     | Monousuario (reparación/root)   | Monousuario                         |
| 2     | Multiusuario sin soporte de red | Multiusuario completo (por defecto) |
| 3-4   | Multiusuario con soporte de red | Igual que el nivel 2                |
| 5     | Multiusuario gráfico (X11)      | Igual que el nivel 2                |
| 6     | Reiniciar el sistema            | Reiniciar                           |

### Comandos SysVinit
*  `runlevel`: Indica el nivel de ejecución actual .
*  `init` o `telinit`: Cambia de un nivel de ejecución a otro .
*  `update-rc.d [script] enable/disable [level]`: Configura scripts para niveles específicos .