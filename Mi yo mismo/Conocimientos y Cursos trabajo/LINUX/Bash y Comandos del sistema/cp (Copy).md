
Copia archivos o directorios de un origen a un destino.

- **Opciones clave**:
    
    - `cp -r`: (Recursive) Obligatorio para copiar **directorios** con todo su contenido.
        
    - `cp -p`: Preserva los atributos (permisos y fechas originales).
        
    - `cp -u`: (Update) Solo copia si el origen es más nuevo que el destino o si el archivo no existe.
        
- **Ejemplo**: `cp -rp /home/user/documentos /backup/`
