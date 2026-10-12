---
tipo: concepto
estado: Activo
nivel: Básico
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Llaves primarias y foráneas

## ¿Qué es?
Las claves primarias y foráneas son los mecanismos de enlace estructurales del modelo relacional:

- **Clave Primaria (Primary Key o PK)**: Columna o combinación de columnas cuyos valores identifican de modo unívoco e irreductible cada registro de una tabla. No admite valores duplicados ni nulos (ver [[Ningún atributo de la clave primaria puede ser nulo]]).
- **Clave Foránea (Foreign Key o FK)**: Columna o conjunto de columnas en una tabla cuyos valores hacen referencia directa a la clave primaria de otra tabla (o de la misma tabla). Garantiza la integridad referencial de los vínculos (ver [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]).

## Contexto y Aplicación
Al pasar del esquema conceptual Entidad/Relación al esquema lógico relacional, se deben añadir formalmente las **claves foráneas** necesarias para materializar las interrelaciones entre las entidades. Dichas claves foráneas **no aparecen representadas gráficamente en el diagrama E/R** original, sino que surgen durante la traducción relacional.

En el ejemplo del manual (base de datos **Escuela**), las relaciones se implementan mediante las siguientes conexiones de PK y FK:

```mermaid
erDiagram
    ESCUELA ||--o{ DOCENTE : "1:N"
    DOCENTE ||--|{ ASIGNATURA : "1:N"
    ESTUDIANTE ||--o| BECA : "1:1"
    ESTUDIANTE ||--o{ TEMA : "1:N"

    ESCUELA {
        int Id_Escuela PK
        string Nombre
    }
    DOCENTE {
        int Id_Docente PK
        int Id_Escuela FK
        string Nombre
        string Sexo
        string Telefono
    }
    ASIGNATURA {
        int Id_Asignatura PK
        int Id_Docente FK
        string Nombre
    }
    ESTUDIANTE {
        int Id_Estudiante PK
        string Nombre_Estudiante
        string Sexo
        date Fecha_Nac
    }
    BECA {
        int Id_Beca PK
        int Id_Estudiante FK
        float Cuantia
        date Fecha
    }
    TEMA {
        int Id_Tema PK
        int Id_Estudiante FK
        string Titulo
    }
```

## Relacionado con
- [[Restricciones de la base de datos]]
- [[Reglas de integridad y semántica de datos]]
- [[Ningún atributo de la clave primaria puede ser nulo]]
- [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]
- [[Modelo Entidad-Relación]]
- [[Cardinalidad]]
- [[Diseño lógico de la base de datos]]
- [[Normalización de tablas]]
- [[Normalizar una estructura de datos hasta tercera forma normal]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- Ninguno por el momento.
