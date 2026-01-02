### Diferencia clave

| Comando | Uso |
|------|----|
| df | Espacio libre/usado de particiones |
| du | Espacio ocupado por archivos/directorios |

---

## 📊 Comando df

```bash
df -h
```

Muestra:
- Tamaño total
- Usado
- Libre
- Punto de montaje

Ejemplo:
```bash
df -h /home
```

---

## 📦 Comando du – Ejemplos explicados

### Tamaño total del directorio actual
```bash
du -sh .
```
Muestra **el tamaño total del directorio actual**.

---

### Tamaño detallado del directorio actual
```bash
du -h *
```
Muestra **el tamaño de cada archivo y subdirectorio**.

---

### Tamaño total de todo el sistema
```bash
du -sh /
```
Muestra el tamaño total del sistema de archivos.

⚠️ Recomendado:
```bash
sudo du -sh /
```

---

### Tamaño de todos los directorios principales del sistema
```bash
du -h /*
```
Permite identificar rápidamente qué directorios consumen más espacio.

Ejemplo:
```text
6.2G /usr
1.5G /home
800M /var
```

---

## 🧠 Resumen rápido

| Comando                                         | Resultado                                                                                            |
| ----------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `df -h`                                         | Estado de particiones                                                                                |
| `du -sh .`                                      | Tamaño total directorio actual                                                                       |
| `du -h *`                                       | Detalle por archivo                                                                                  |
| `du -sh /`                                      | Tamaño total del sistema                                                                             |
| `du -h /*`                                      | Tamaño de directorios principales                                                                    |
| du -sh /*  \| sort -h                           | Ordena la salida de menor a mayor en formato humano                                                  |
| `du -sh /* 2> /dev/null \| sort -h \| tail -n1` | Ordena la salida de menor a mayor en formato humano no muestra los errores de archivos no accesibles |

---

## ✅ Buenas prácticas

- Usar `df` para detectar falta de espacio
- Usar `du` para localizar el origen del problema
- Usar `sudo` para resultados completos


