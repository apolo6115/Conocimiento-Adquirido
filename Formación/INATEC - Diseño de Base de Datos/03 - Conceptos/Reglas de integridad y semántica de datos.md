---
tipo: concepto
estado: Activo
nivel: Intermedio
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Reglas de integridad y semántica de datos

## ¿Qué es?
La integridad de datos en el modelo relacional garantiza que la información almacenada sea precisa, consistente y confiable a lo largo del tiempo. Los pilares fundamentales de la integridad son las **llaves primarias**, las **llaves foráneas**, el manejo de **valores nulos** y las dos **reglas de integridad relacional**:

1. **Integridad de Entidades**: Ningún componente de la clave primaria puede aceptar valores nulos (ver regla [[Ningún atributo de la clave primaria puede ser nulo]]).
2. **Integridad Referencial**: Toda clave foránea debe coincidir con un valor existente de clave primaria o ser nula (ver regla [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]).

### Semántica de los Valores Nulos
Cuando en una fila o tupla el valor de un atributo es desconocido, se clasifica como **nulo (`NULL`)**:
- Un valor nulo **no** representa el número cero ni una cadena de texto vacía `""`, ya que estos últimos son valores definidos con significado semántico.
- El nulo denota **ausencia total de información**, ya sea por desconocimiento temporal del dato al momento de inserción o porque el atributo carece de aplicabilidad para ese registro particular.

Casos frecuentes de aplicación del valor nulo:
- Creación de un registro preliminar cuando aún no se recopilan la totalidad de atributos.
- Alteración de una tabla preexistente (`ALTER TABLE ADD COLUMN`) donde los registros históricos carecen inicialmente de dicho dato.
- Exclusión deliberada de registros en agregaciones o cálculos numéricos (`AVG`, `SUM`).

## Contexto y Aplicación
Las reglas de integridad y la semántica de datos se materializan durante la definición del esquema relacional y se programan en el SGBD mediante las [[Restricciones de la base de datos]] (`PRIMARY KEY`, `FOREIGN KEY`, `NOT NULL`, `CHECK`). 

Aseguran que las transacciones y operaciones concurrentes de usuarios y aplicaciones nunca corrompan los datos ni generen registros huérfanos o inconsistencias lógicas.

## Relacionado con
- [[Ningún atributo de la clave primaria puede ser nulo]]
- [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]
- [[Llaves primarias y foráneas]]
- [[Restricciones de la base de datos]]
- [[Diseño lógico de la base de datos]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- Ninguno por el momento.
