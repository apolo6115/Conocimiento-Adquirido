---
tipo: concepto
estado: Activo
nivel: Básico
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Diseño lógico de la base de datos

## ¿Qué es?
El diseño lógico es la conversión del esquema conceptual de datos en un esquema lógico. Es una descripción formal y estructurada de la base de datos que puede procesar un Sistema de Gestión de Bases de Datos (SGBD).

Su objetivo principal es obtener una representación que use de la manera más eficiente posible los recursos disponibles para la estructuración de datos y el modelado de restricciones en el modelo lógico relacional.

La estructura relacional se representa como un conjunto de tablas bidimensionales:
- **Filas (Tuplas o Registros)**: Corresponden a instancias individuales de una entidad.
- **Columnas (Campos o Atributos)**: Corresponden a las propiedades o características de esos registros.

```mermaid
flowchart LR
    A["1. Requisitos<br>(Lenguaje natural)"] --> B["2. Diseño Conceptual<br>(Modelo E/R)"]
    B --> C["3. Diseño Lógico<br>(Modelo Relacional)"]
    C --> D["4. Diseño Físico<br>(SQL / Tablas)"]
```

## Contexto y Aplicación
El diseño lógico se sitúa como la fase de transición entre el diagrama abstracto de negocio y la implementación física en la base de datos:

1. **Transformación desde el Modelo E/R**:
   - Cada entidad del modelo E/R se convierte en una tabla relacional.
   - Al pasar del esquema E/R al relacional se deben incorporar las **claves foráneas** necesarias para materializar las interrelaciones. Dichas claves foráneas **no aparecen representadas** en el esquema E/R original (ver [[Llaves primarias y foráneas]]).
2. **Consideraciones de Atributos**:
   - Según el dominio, el diseño lógico incorpora atributos sociodemográficos como variables de sexo (Mujer – Hombre) o género (Femenino – Masculino) para caracterizar la población usuaria del sistema.
3. **Optimización y Reglas**:
   - El esquema lógico se depura aplicando las [[Formas Normales]] para erradicar anomalías y redundancias (ver [[Normalizar una estructura de datos hasta tercera forma normal]]).
   - Se aplican las restricciones de integridad de entidades ([[Ningún atributo de la clave primaria puede ser nulo]]) y de integridad referencial ([[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]).

## Relacionado con
- [[Modelo Entidad-Relación]]
- [[Cardinalidad]]
- [[Formas Normales]]
- [[Normalización de tablas]]
- [[Normalizar una estructura de datos hasta tercera forma normal]]
- [[Llaves primarias y foráneas]]
- [[Restricciones de la base de datos]]
- [[Reglas de integridad y semántica de datos]]
- [[Ningún atributo de la clave primaria puede ser nulo]]
- [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- El manual de INATEC no detalla herramientas específicas CASE para la generación automatizada del esquema lógico (DDL).
