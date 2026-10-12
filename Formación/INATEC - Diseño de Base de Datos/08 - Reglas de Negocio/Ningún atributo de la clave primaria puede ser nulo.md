---
tipo: regla
estado: Activo
nivel: Avanzado
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Ningún atributo de la clave primaria puede ser nulo

## Regla de Negocio
En toda relación base del modelo relacional, ningún atributo que forme parte de una **clave primaria (Primary Key)** puede aceptar valores nulos. Cada tupla o fila debe poseer una identificación completa y unívoca.

## Justificación / Política
Una clave primaria es un identificador **irreducible** utilizado para identificar de modo único las filas de una tabla:
- **Irreductibilidad**: Significa que ningún subconjunto propio de los atributos de la clave primaria es suficiente para identificar las filas de modo unívoco.
- Si se permitiese que un atributo de la clave primaria fuese nulo, se asumiría que dicho atributo no es estrictamente indispensable para distinguir la fila, lo cual contradice el principio de irreductibilidad y compromete la integridad de entidades del sistema de gestión de bases de datos (SGBD).

## Excepciones
Ninguna. La regla de integridad de entidades no admite excepciones en tablas base del modelo relacional. Si un registro no posee clave primaria completa y definida, no puede ser insertado en la base de datos.

## Relacionado con
- [[Reglas de integridad y semántica de datos]]
- [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]
- [[Llaves primarias y foráneas]]
- [[Restricciones de la base de datos]]
- [[Normalización de tablas]]
- [[Normalizar una estructura de datos hasta tercera forma normal]]
- [[Diseño lógico de la base de datos]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- Ninguno por el momento.
