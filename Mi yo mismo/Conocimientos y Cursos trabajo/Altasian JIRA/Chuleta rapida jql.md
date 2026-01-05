# 🧠 JQL (Jira Query Language) – Resumen y Guía Rápida

## ¿Qué es JQL?
JQL (Jira Query Language) es un lenguaje de consultas que permite buscar, filtrar y ordenar incidencias en Jira de forma avanzada, mucho más potente que la búsqueda básica.

Permite:
- Crear búsquedas precisas
- Combinar múltiples condiciones
- Usar lógica booleana
- Guardar filtros reutilizables
- Ordenar resultados

---




## 🧱 Estructura básica de JQL

```
CAMPO OPERADOR VALOR
```

Ejemplo:
```
project = TEST AND status = "In Progress"
```

También se puede ordenar:
```
ORDER BY priority DESC
```

---

## 🧩 Campos comunes

- project
- status
- assignee
- reporter
- priority
- issuetype
- created
- updated
- resolution

---

## 🔢 Operadores comunes

| Operador | Descripción |
|--------|------------|
| = | Igual |
| != | Distinto |
| > | Mayor que |
| < | Menor que |
| >= | Mayor o igual |
| <= | Menor o igual |
| IN | Dentro de una lista |
| NOT IN | No está en una lista |
| IS EMPTY | Campo vacío |
| IS NOT EMPTY | Campo no vacío |

---

## 🔀 Palabras clave lógicas

- AND → Todas las condiciones deben cumplirse
- OR → Al menos una condición se cumple
- NOT → Niega una condición

Ejemplo:
```
status = Open AND priority = High
```

---

## 📅 Funciones útiles

- currentUser()
- startOfDay()
- endOfDay()
- -1d, -1w, -1M (fechas relativas)
- membersOf("group-name")

Ejemplo:
```
assignee = currentUser() AND created > -7d
```

---

## 📌 Ejemplos prácticos

### Issues abiertas asignadas a mí
```
assignee = currentUser() AND status != Done
```

### Bugs críticos en varios proyectos
```
project IN (APP, WEB) AND issuetype = Bug AND priority IN (Blocker, Critical)
```

### Issues sin asignar
```
assignee IS EMPTY
```

### Issues recientes
```
created > -3d ORDER BY created DESC
```

---

## 💡 Tips rápidos

- Usa comillas para valores con espacios
- Jira autocompleta campos y operadores
- Guarda tus búsquedas como filtros
- Usa paréntesis para lógica compleja

Ejemplo:
```
(project = APP OR project = WEB) AND status = Open
```

---

## 🧾 Ideal para Obsidian
Este archivo está pensado como nota Markdown reutilizable en Obsidian o cualquier editor MD.
