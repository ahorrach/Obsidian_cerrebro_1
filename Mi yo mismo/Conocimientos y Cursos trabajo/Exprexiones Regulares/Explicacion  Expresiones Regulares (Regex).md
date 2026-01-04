
Resumen y **chuleta rápida** con ejemplos prácticos en **Java**, **Python** y **comandos Linux**, pensada para **Obsidian (Markdown)**.

---

## 🔹 ¿Qué son las expresiones regulares?
Las **expresiones regulares (regex)** son patrones usados para **buscar, validar, extraer o reemplazar texto**.

Se usan para:
- Validar emails, teléfonos, contraseñas
- Buscar palabras o formatos específicos
- Reemplazar texto
- Extraer datos

---

## 🔹 Sintaxis básica

| Símbolo | Significado | Ejemplo |
|------|-----------|--------|
| `.` | Cualquier carácter | `a.c` → abc, a1c |
| `^` | Inicio de línea | `^Hola` |
| `$` | Fin de línea | `mundo$` |
| `*` | 0 o más | `a*` |
| `+` | 1 o más | `a+` |
| `?` | 0 o 1 | `colou?r` |
| `{n}` | Exactamente n | `\d{3}` |
| `{n,m}` | Entre n y m | `\d{2,4}` |
| `[]` | Conjunto | `[abc]` |
| `[^ ]` | Negación | `[^0-9]` |
| `|` | OR | `a|b` |
| `()` | Grupo | `(ab)+` |

---

## 🔹 Clases comunes

| Patrón | Significado |
|------|------------|
| `\d` | Dígito (0-9) |
| `\D` | No dígito |
| `\w` | Letra, número o _ |
| `\W` | No palabra |
| `\s` | Espacio en blanco |
| `\S` | No espacio |

---

## 🔹 Ejemplos de patrones útiles

### Email
```regex
^[\w.-]+@[\w.-]+\.[a-zA-Z]{2,}$
```

### Número de teléfono (simple)
```regex
^\d{9}$
```

### Fecha (dd/mm/yyyy)
```regex
^(0[1-9]|[12][0-9]|3[01])/(0[1-9]|1[0-2])/\d{4}$
```

---

## ☕ Regex en **Java**

### Validar email
```java
import java.util.regex.*;

String email = "test@mail.com";
Pattern p = Pattern.compile("^[\\w.-]+@[\\w.-]+\\.[a-zA-Z]{2,}$");
Matcher m = p.matcher(email);

if (m.matches()) {
    System.out.println("Email válido");
}
```

### Buscar coincidencias
```java
Pattern p = Pattern.compile("\\d+");
Matcher m = p.matcher("Hay 123 números");

while (m.find()) {
    System.out.println(m.group());
}
```

---

## 🐍 Regex en **Python**

Módulo: `re`

### Validar patrón
```python
import re

email = "test@mail.com"
if re.match(r"^[\w.-]+@[\w.-]+\.[a-zA-Z]{2,}$", email):
    print("Email válido")
```

### Buscar todas las coincidencias
```python
texto = "Tengo 2 gatos y 3 perros"
numeros = re.findall(r"\d+", texto)
print(numeros)
```

### Reemplazar texto
```python
re.sub(r"\s+", "-", "hola mundo regex")
```

---

## 🐧 Regex en **Linux**

### `grep`
Buscar líneas que contengan números:
```bash
grep "[0-9]" archivo.txt
```

Buscar email:
```bash
grep -E "[\\w.-]+@[\\w.-]+\\.[a-zA-Z]{2,}" archivo.txt
```

---

### `sed` (reemplazo)

Reemplazar espacios por guiones:
```bash
sed 's/ /-/g' archivo.txt
```

Eliminar números:
```bash
sed 's/[0-9]//g' archivo.txt
```

---

### `awk`

Mostrar líneas que empiecen con una palabra:
```bash
awk '/^ERROR/' archivo.log
```

---

## ⚡ Chuleta ultra rápida

```text
^      inicio
$      fin
.      cualquier carácter
*      0 o más
+      1 o más
?      opcional
{n,m}  repeticiones
\d     dígito
\w     palabra
\s     espacio
|      OR
[]     conjunto
()     grupo
```

---

## 📎 Consejos
- En **Java** hay que **doblar las barras** `\\`
- En **Python** usa strings crudos: `r"regex"`
- Prueba regex en: regex101.com
- Empieza simple y ve refinando

---
