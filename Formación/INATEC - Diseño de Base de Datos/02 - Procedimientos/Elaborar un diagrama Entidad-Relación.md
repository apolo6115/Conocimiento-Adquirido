---
tipo: procedimiento
estado: Activo
nivel: Básico
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Elaborar un diagrama Entidad-Relación

## Objetivo
Representar visualmente las entidades de un sistema y las relaciones entre ellas mediante un diagrama Entidad-Relación (ER). Ver definición en [[Modelo Entidad-Relación]].

## Requisitos Previos
- Conocer las entidades del sistema a modelar (suelen ser los sustantivos de las descripciones, reglas o narrativas).
- Identificar los atributos de cada entidad y la naturaleza de las relaciones.

## Pasos a Seguir
1. Escribir los nombres de las entidades y dibujar un rectángulo alrededor de cada uno. Por ejemplo, en el registro de estudiantes las entidades podrían ser Estudiantes, Beca, Docentes.
2. Dibujar una línea entre las entidades que tengan relación entre sí. Dibujar un rombo en cada línea y escribir en él la naturaleza de la relación. Por ejemplo, entre Estudiante y Beca escribir "obtiene".
3. Añadir los atributos en círculos (óvalos) y conectarlos a las entidades relacionadas con líneas. Por ejemplo, nombre del estudiante, sexo, fecha de nacimiento.
4. Añadir la [[Cardinalidad]] o el número de elementos de cada entidad. Por ejemplo, si un estudiante puede tener una beca, se añade la línea correspondiente.

## Validación
El diagrama es correcto cuando contiene los tres tipos de elementos —entidades, atributos y relaciones— y cada relación tiene definida su cardinalidad.

## Relacionado con
- [[Modelo Entidad-Relación]]
- [[Cardinalidad]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- Ninguno por el momento.
