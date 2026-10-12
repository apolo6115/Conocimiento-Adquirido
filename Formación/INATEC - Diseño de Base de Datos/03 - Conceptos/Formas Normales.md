---
tipo: concepto
estado: Activo
nivel: Intermedio
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Formas Normales

## ¿Qué es?
Las **formas normales (NF)** proporcionan los criterios para determinar el grado de vulnerabilidad de una tabla a inconsistencias y anomalías lógicas. Cuanta más alta sea la forma normal aplicable a una tabla, menos vulnerable será a inconsistencias y anomalías.

La **normalización** es la transformación de las vistas complejas y del almacén de datos a un conjunto de estructuras de datos más pequeñas y estables. Además de ser más simples y estables, las estructuras de datos resultantes son más fáciles de mantener que otras estructuras (Kendall, 2005).

## Contexto y Aplicación
La aplicación sucesiva de las formas normales (1FN, 2FN, 3FN) se detalla en [[Normalización de tablas]]. Se aplican sobre la estructura lógica de las tablas definida en el [[Diseño lógico de la base de datos]].

## Relacionado con
- [[Normalización de tablas]]
- [[Normalizar una estructura de datos hasta tercera forma normal]]
- [[Diseño lógico de la base de datos]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- El manual solo desarrolla hasta la Tercera Forma Normal (3FN); no se detallan FN superiores (BCNF, 4FN, 5FN).
