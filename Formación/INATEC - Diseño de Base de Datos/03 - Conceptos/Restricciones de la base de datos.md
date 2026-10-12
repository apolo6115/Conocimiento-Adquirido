---
tipo: concepto
estado: Activo
nivel: Intermedio
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Restricciones de la base de datos

## ¿Qué es?
Una **restricción** es una condición de obligado cumplimiento por los datos de la base de datos. El manual distingue dos orígenes.

## Restricciones por ser una base de datos relacional
- No puede haber dos filas iguales.
- El orden de las filas no es significativo.
- El orden de los atributos no es significativo.
- Cada atributo solo puede tomar un valor en el dominio en el que está inscrito.

## Restricciones incorporadas por los usuarios
Una vez dado un nombre y definida una tabla, se establecen ciertas restricciones para cada columna o para toda la tabla, que deberán cumplirse.

| Restricción | Descripción |
|---|---|
| `UNIQUE (columna [, columna...])` | El conjunto de columnas especificadas no puede tener valores repetidos. Es una clave alternativa. |
| `PRIMARY KEY (columna [, columna...])` | El conjunto de columnas especificadas no puede tener valores nulos ni repetidos. Es una clave primaria. |
| `FOREIGN KEY (columna [, columna...]) REFERENCES tabla [(columna2 [, columna2...])]` | El conjunto de columnas especificadas es una clave foránea que referencia la clave primaria de otra tabla. |
| `CHECK (condiciones)` | La tabla debe cumplir las condiciones especificadas. |

## Contexto y Aplicación
Las restricciones se emplean al implementar físicamente el modelo; se apoyan en las [[Llaves primarias y foráneas]] y se relacionan con las [[Reglas de integridad y semántica de datos]].

## Relacionado con
- [[Llaves primarias y foráneas]]
- [[Reglas de integridad y semántica de datos]]
- [[Ningún atributo de la clave primaria puede ser nulo]]
- [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]
- [[Diseño lógico de la base de datos]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- Ninguno por el momento.
