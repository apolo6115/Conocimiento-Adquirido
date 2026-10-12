---
tipo: regla
estado: Activo
nivel: Avanzado
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Las claves foráneas deben referenciar claves primarias válidas o ser nulas

## Regla de Negocio
En toda relación del modelo relacional donde exista una **clave ajena o foránea (Foreign Key)**, los valores de dicha clave deben coincidir exactamente con valores existentes de la clave primaria a la que hace referencia, o bien, ser completamente nulos.

## Justificación / Política
Esta regla constituye el principio de **integridad referencial** del modelo relacional:
- Garantiza que las relaciones entre dos tablas permanezcan sincronizadas durante las operaciones de inserción, actualización y eliminación.
- Evita la existencia de registros "huérfanos" (por ejemplo, un estudiante asignado a un aula o beca inexistente).
- Define formalmente los estados válidos (legales) e inválidos (ilegales) de la base de datos.

## Excepciones
La regla no prohíbe que el valor sea nulo (a menos que la columna esté definida explícitamente como `NOT NULL`), lo que permite que una entidad no esté necesariamente vinculada a otra en un momento dado (por ejemplo, un estudiante que aún no posee beca asignada).

Ante una transacción que intente generar un estado ilegal (como borrar un registro padre que tiene hijos referenciados), el SGBD debe:
1. **Rechazar la operación**: abortar la transacción (comportamiento `RESTRICT` / `NO ACTION`).
2. **Operación compensatoria**: ejecutar una acción compensatoria autorizada (`CASCADE` para eliminar en cascada, o `SET NULL` para neutralizar la referencia).

## Relacionado con
- [[Reglas de integridad y semántica de datos]]
- [[Ningún atributo de la clave primaria puede ser nulo]]
- [[Llaves primarias y foráneas]]
- [[Restricciones de la base de datos]]
- [[Normalización de tablas]]
- [[Normalizar una estructura de datos hasta tercera forma normal]]
- [[Diseño lógico de la base de datos]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- Ninguno por el momento.
