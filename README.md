# Web de consulta de coseguros AEO

Archivos que se publican juntos en el hosting:

- `index.html`: la web.
- `aranceles.xls` (o `aranceles.xlsx`): el Excel de aranceles. Si existen los dos, se usa el `.xlsx`.

## Cómo actualiza Javier los valores

1. Edita el Excel como siempre (mismo formato: código en la columna A, nombre en la B, honorarios en la C, y los encabezados "PLAN 401", "PLAN A 403", etc. con el porcentaje de cada plan en la fila de arriba).
2. Lo guarda con el nombre `aranceles.xls` (o `aranceles.xlsx`) y reemplaza el archivo en el hosting.
3. La web toma los valores nuevos al recargar. No hay que tocar nada más.

La web calcula el coseguro como honorario × porcentaje del plan, redondeado a $100. Ignora las columnas de valores ya calculados del Excel.
Si se agrega un plan nuevo, basta con agregar su columna "PLAN ..." con el porcentaje arriba.

## Cómo marcar las prácticas auditables

Están en el archivo `auditables.csv`, aparte del Excel de aranceles, así no se pierden cuando se reemplaza el Excel.
Va un dato por línea, y puede ser:

- un código completo, por ejemplo `TQ.06.03`, para una sola práctica;
- un prefijo, por ejemplo `TQ` (todos los tratamientos quirúrgicos) o `TQ.06` (todas las operaciones del cristalino).

Hoy tiene `PE`, `TL` y `TQ`: todo es auditable menos las Prácticas Comunes (PC).
Se edita desde github.com abriendo el archivo y tocando el lápiz. Esas prácticas muestran "Coseguro definido por auditor" en lugar del valor.

También se puede usar una hoja llamada `AUDITABLES` dentro del Excel, con el mismo formato.
