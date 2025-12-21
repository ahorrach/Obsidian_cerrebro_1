*  **Initramfs (initial ram file system):** Es un sistema de archivos ram inicial (ramdisk) . 
*  Consiste en un archivo comprimido (normalmente gzip) con un sistema de archivos mínimo que se carga en RAM .
*  El kernel lo usa para cargar módulos y controladores antes de montar el sistema de archivos raíz real e invocar al proceso init .
*  En la configuración de GRUB aparece como la línea `initrd` seguida de la ruta de la imagen .
