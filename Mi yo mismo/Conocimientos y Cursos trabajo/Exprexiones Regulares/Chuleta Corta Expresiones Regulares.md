------
Las expresiones regulares son patrones para buscar, validar, extraer y reemplazar texto.
Se usan en validaciones, parsing de logs, búsqueda avanzada y automatización.

--------------------------------------------------
SINTAXIS BASICA
--------------------------------------------------
.        Cualquier carácter
^        Inicio de línea
$        Fin de línea
*        0 o más repeticiones
+        1 o más repeticiones
?        0 o 1 (opcional)
{n}      Exactamente n veces
{n,m}    Entre n y m veces
[]       Conjunto de caracteres
[^ ]     Negación
|        OR lógico
()       Grupo

--------------------------------------------------
CLASES COMUNES
--------------------------------------------------
\d       Dígito (0-9)
\D       No dígito
\w       Letra, número o _
\W       No palabra
\s       Espacio en blanco
\S       No espacio

--------------------------------------------------
PATRONES UTILES
--------------------------------------------------
Email:
^[\w.-]+@[\w.-]+\.[a-zA-Z]{2,}$

Teléfono (9 dígitos):
^\d{9}$

Fecha (dd/mm/yyyy):
^(0[1-9]|[12][0-9]|3[01])/(0[1-9]|1[0-2])/\d{4}$

--------------------------------------------------
JAVA
--------------------------------------------------
Validar email:

Pattern p = Pattern.compile("^[\\w.-]+@[\\w.-]+\\.[a-zA-Z]{2,}$");
Matcher m = p.matcher(email);
if (m.matches()) { }

Buscar números:

Pattern p = Pattern.compile("\\d+");
Matcher m = p.matcher(texto);
while (m.find()) {
    System.out.println(m.group());
}

--------------------------------------------------
PYTHON
--------------------------------------------------
import re

Validar email:
re.match(r"^[\w.-]+@[\w.-]+\.[a-zA-Z]{2,}$", email)

Buscar coincidencias:
re.findall(r"\d+", texto)

Reemplazar:
re.sub(r"\s+", "-", texto)

--------------------------------------------------
LINUX
--------------------------------------------------
GREP:

grep "[0-9]" archivo.txt
grep -E "[\\w.-]+@[\\w.-]+\\.[a-zA-Z]{2,}" archivo.txt

SED:

sed 's/ /-/g' archivo.txt
sed 's/[0-9]//g' archivo.txt

AWK:

awk '/^ERROR/' archivo.log

==================================================
CHULETA ULTRA CORTA
==================================================
^   inicio     $   fin
.   cualquiera
*   0+     +   1+     ? opcional
{n,m} repeticiones
\d  dígito   \w palabra   \s espacio
[]  conjunto   | OR   () grupo

TIP:
Java => usar \\\\
Python => usar r"regex"

