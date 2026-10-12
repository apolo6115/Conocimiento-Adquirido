---
tipo: concepto
estado: Activo
nivel: Avanzado
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Normalización de tablas

## ¿Qué es?
La normalización es el proceso de diseño relacional que consiste en descomponer y estructurar tablas complejas en esquemas más pequeños y estables mediante la aplicación sucesiva de las [[Formas Normales]].

Su finalidad fundamental es eliminar la redundancia de datos, evitar anomalías en operaciones de inserción, actualización y borrado, y asegurar la integridad referencial.

### 1FN – Primera Forma Normal
Una tabla está en 1FN si:
- Todos sus atributos son **atómicos** (cada celda contiene un único valor escalar indivisible).
- Posee una **clave primaria única** definida (ej. identificador autoincremental, cédula o código).
- La clave primaria **no contiene valores nulos** ([[Ningún atributo de la clave primaria puede ser nulo]]).
- Posee una estructura homogénea sin variación en la cantidad de columnas por fila.
- Los atributos no clave dependen funcionalmente de la clave primaria.

### 2FN – Segunda Forma Normal
Una tabla está en 2FN si está en 1FN y todos los atributos no clave **dependen de forma completa de la clave principal** (eliminación de dependencias parciales respecto a claves compuestas).

### 3FN – Tercera Forma Normal
Una tabla está en 3FN si está en 2FN y **no existen dependencias transitivas** (ningún atributo no clave depende funcionalmente de otro atributo no clave; todos dependen directamente de la clave primaria).

## Contexto y Aplicación
La normalización se aplica durante la fase de [[Diseño lógico de la base de datos]] antes de generar las tablas físicas finales en SQL. Transforma modelos desordenados o desnormalizados en estructuras altamente eficientes y escalables.

Para la guía paso a paso de ejecución, ver el procedimiento [[Normalizar una estructura de datos hasta tercera forma normal]].

### Comparativa del proceso de normalización (Ejemplo Manual INATEC)

1. **Tabla sin normalizar (Anomalía de grupos repetitivos)**:
| Id_Estudiante | Nombre_Estudiante | Sexo | Docente | Asig1 | Asig2 | Asig3 |
|---|---|---|---|---|---|---|
| 100 | Mercedes Ramos | M | Juana Medina | 111-01 | 111-02 | 111-03 |
| 101 | Nidia Pereira | M | Francisco Cruz | 222-01 | 222-02 | 222-03 |

2. **1FN (Desglose en tuplas atómicas)**: Se genera una fila por cada asignatura para cada estudiante.
3. **2FN (Separación de entidades)**: Se dividen en tabla `Estudiante` y tabla `Asignaturas`.
4. **3FN (Eliminación de dependencia transitiva)**: Se extrae la tabla `Aula` (`Docente`, `Código_Aula`, `Nombre_Aula`), enlazada mediante claves foráneas.

## Relacionado con
- [[Formas Normales]]
- [[Normalizar una estructura de datos hasta tercera forma normal]]
- [[Diseño lógico de la base de datos]]
- [[Llaves primarias y foráneas]]
- [[Ningún atributo de la clave primaria puede ser nulo]]
- [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- Ninguno por el momento.
