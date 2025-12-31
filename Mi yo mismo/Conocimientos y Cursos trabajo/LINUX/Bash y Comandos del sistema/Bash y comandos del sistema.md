

Comandos del sistema:
# Comandos de BASH y Entorno

El intérprete **BASH** utiliza tanto comandos internos como ejecutables externos.

## 1. [[Identificación y Localización (type , which , $PATH )]]
    

## 2. [[Configuración del Entorno (set, export, unset, env,export,unset,env,history)]]

## 3. Visualización con `echo`

El comando **`echo`** muestra el texto que recibe en la salida estándar.

- **`-e`**: Habilita la interpretación de caracteres especiales escapados con contrabarra (`\`), como `\n` para saltos de línea.
    
- **Comillas**:
    
    - **Simples (`'`)**: Tratan todo como texto literal (ej. `'$RANDOM'` no se procesa).
        
    - **Dobles (`"`)**: Permiten la interpretación de variables especiales (ej. `"$RANDOM"` muestra un número).
        

## 4. Ayuda e Información del Sistema

- **`man`**: Accede a los manuales de ayuda de comandos y ficheros de configuración.
    
- **`uname`**: Muestra información del sistema operativo.
    
    - **`-a`**: Muestra toda la información disponible (kernel, arquitectura, etc.).
        


[[Atajos BASH FLASHCARD]]
[[CHULETA DE ATAJOS DE BASH]]


# 📋 Resumen de Comandos de Archivos y Texto

| Comando                                 | Opciones Clave               | Propósito                                                              |
| --------------------------------------- | ---------------------------- | ---------------------------------------------------------------------- |
| **`wc`**                                | `-l`, `-w`, `-c`             | Contar líneas, palabras o bytes/caracteres.                            |
| uniq                                    | `-c`, `-d`                   | Contar ocurrencias o mostrar solo líneas duplicadas.                   |
| **`sort`**                              | `-n`, `-h`, `-r`             | Ordenar líneas numéricamente, por tamaño humano o inversamente.        |
| **`rm`**                                | `-r`, `-f`                   | Borrar archivos o directorios de forma recursiva y forzada.            |
| **`rev`**                               |                              | Invertir el orden de los caracteres de cada línea.                     |
| [[mv (Move) \| mv]]                     |                              | Mover o renombrar archivos.                                            |
| [[ls (List) \| ls]]                     | `-l`, `-h`, `-S`, `-t`, `-r` | Listar archivos con detalles, tamaño humano, orden por tamaño o fecha. |
| [[Análisis de Disco Comando "du"\| du]] |                              | Analisis de uso de disco (disck usage)                                 |
| [[cp (Copy) \| cp]]                     | `-r`, `-p`                   | Copiar archivos/directorios preservando atributos.                     |
| [[mkdir (Make Directory) \| mkdir]]     | `-p`                         | Crear directorios (incluyendo padres si faltan).                       |
