`rm` (Remove)

Borra archivos o directorios. **Cuidado:** No hay "papelera de reciclaje" en la terminal; lo que borras desaparece.

- **Opciones clave**:
    
    - `rm -r`: (Recursive) Borra directorios y todo su contenido.
        
    - `rm -f`: (Force) Borra sin preguntar y omite archivos que no existen.
        
    - `rm -i`: Modo interactivo; te pregunta antes de borrar cada archivo (seguridad).
        
- **Peligro**: `sudo rm -rf /` intentaría borrar todo el sistema.