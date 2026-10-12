---
tipo: procedimiento
estado: Activo
nivel: Intermedio
autor: Leonel
fecha_creacion: 2026-10-11
ultima_revision: 2026-10-11
---

# Normalizar una estructura de datos hasta tercera forma normal

## Objetivo
Transformar una tabla o almacén de datos con anomalías y redundancias a un conjunto de estructuras relacionales en Tercera Forma Normal (3FN), garantizando atomicidad, integridad y consistencia lógica.

## Requisitos Previos
- Contar con la tabla o registro inicial no normalizado.
- Haber identificado los atributos de la entidad y las claves candidatas.
- Conocer los conceptos teóricos de [[Formas Normales]] y [[Normalización de tablas]].

## Pasos a Seguir

### Paso 1: Aplicar la Primera Forma Normal (1FN)
1. **Verificar atomicidad**: Asegurar que cada celda contenga un único valor indivisible (por ejemplo, evitar columnas repetitivas como `Asig1`, `Asig2`, `Asig3` o listas de teléfonos en un solo campo).
2. **Definir una clave primaria única**: Asignar un identificador irreductible (`Id_Estudiante`, cédula o identificador autoincremental). Si no posee clave, no está en 1FN.
3. **Asegurar ausencia de nulos en la clave**: Ninguna fila puede carecer de valor en su clave primaria.
4. **Homogeneizar el esquema**: Comprobar que todas las filas posean exactamente la misma cantidad de columnas.
5. **Validar dependencia funcional**: Comprobar que los atributos no clave dependan directamente de la clave primaria.

*Resultado de 1FN*: Se eliminan grupos repetidos, obteniendo una fila por cada combinación de entidad y atributo.

### Paso 2: Aplicar la Segunda Forma Normal (2FN)
1. Verificar que la tabla cumpla con los requisitos de 1FN.
2. **Identificar dependencias parciales**: Detectar atributos que solo dependen de una parte de una clave compuesta o que generan redundancias sistemáticas en los registros no clave.
3. **Dividir en dos o más tablas**: Separar la entidad principal de los atributos multivaluados dependientes.
4. **Vincular mediante claves**: Conservar la clave primaria de la tabla principal como clave foránea en la tabla secundaria para mantener la trazabilidad.

*Resultado de 2FN*: Se erradica la redundancia masiva de datos descriptivos.

### Paso 3: Aplicar la Tercera Forma Normal (3FN)
1. Verificar que la estructura cumpla con los requisitos de 2FN.
2. **Detectar dependencias transitivas**: Identificar atributos que no dependen de la clave principal, sino de otro atributo no clave (por ejemplo: el aula y código de aula dependen del docente, no del estudiante).
3. **Extraer a una tabla independiente**: Mover los atributos transitivos (`Código_Aula`, `Nombre_Aula`) a una tabla propia (`Aula`).
4. **Establecer claves foráneas**: Relacionar las tablas resultantes mediante claves ajenas ([[Llaves primarias y foráneas]]).

## Ejemplo Práctico (Caso Manual INATEC)

### 1. Estado Inicial (No normalizado)
| Id_Estudiante | Nombre_Estudiante | Sexo | Docente | Asig1 | Asig2 | Asig3 |
|---|---|---|---|---|---|---|
| 100 | Mercedes Ramos | M | Juana Medina | 111-01 | 111-02 | 111-03 |
| 101 | Nidia Pereira | M | Francisco Cruz | 222-01 | 222-02 | 222-03 |
| 102 | José Martínez | H | Alejandra Martínez | 333-01 | 333-02 | 333-03 |
| 103 | Alexa Pereira | M | Gabriel De Trinidad | 444-01 | 444-02 | 444-03 |

### 2. Tras aplicar 1FN (Eliminar registros repetidos)
Se descomponen las columnas repetidas en registros individuales:
- Se obtiene una fila por cada asignatura asociada al `Id_Estudiante`.

### 3. Tras aplicar 2FN (Eliminar datos redundantes)
Se divide en dos tablas:
- **Tabla Estudiante**: `Id_Estudiante` (PK), `Nombre_Estudiante`, `Sexo`, `Docente`.
- **Tabla Asignaturas**: `Id_Estudiante` (FK), `Asignatura`.

### 4. Tras aplicar 3FN (Eliminar dependencias transitivas)
Se extraen los datos del aula que dependen transitivamente del docente:
- **Tabla Estudiante**: `Id_Estudiante` (PK), `Docente`.
- **Tabla Aula**: `Docente` (FK), `Código_Aula`, `Nombre_Aula`.
- **Tabla Asignatura**: `Id_Estudiante` (FK), `Nombre_Asignatura`.

## Validación
- Toda columna contiene valores atómicos sin repeticiones de columnas vectoriales.
- Cada tabla cuenta con una clave primaria debidamente asignada ([[Ningún atributo de la clave primaria puede ser nulo]]).
- No existen dependencias parciales ni transitivas.
- Las tablas resultantes están enlazadas correctamente mediante claves foráneas íntegras ([[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]).

## Relacionado con
- [[Normalización de tablas]]
- [[Formas Normales]]
- [[Diseño lógico de la base de datos]]
- [[Llaves primarias y foráneas]]
- [[Ningún atributo de la clave primaria puede ser nulo]]
- [[Las claves foráneas deben referenciar claves primarias válidas o ser nulas]]
- [[00 - Unidad 1 - Modelado de la base de datos]]

## Lo que aún no sé
- Si el sistema evaluado requiere normalizaciones superiores (Forma Normal de Boyce-Codd - BCNF o 4FN) en etapas avanzadas de optimización.
