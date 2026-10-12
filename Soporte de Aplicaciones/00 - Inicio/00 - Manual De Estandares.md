---
tipo: concepto
estado: Activo
nivel: Básico
autor: Leonel
fecha_creacion: 2026-10-05
ultima_revision: 2026-10-05
---

# Manual de Estándares del Vault

Este documento define la norma y directrices de organización, nomenclatura y redacción para la base de conocimiento en Obsidian.

---

## 1. Principio Fundamental
- **Solo información confirmada**: Únicamente se documentan hechos verificados en operación real, confirmados por un compañero, documentación oficial o validados en pruebas.
- Cualquier dato no verificado, hipótesis o aspecto pendiente debe ir en la sección `## Lo que aún no sé`.
- **Una nota = una sola pregunta principal**: Mantener notas atómicas y enfocadas.

---

## 2. Estructura de Carpetas

### Soporte de Aplicaciones (`Soporte de Aplicaciones/01 - Aplicaciones/<APP>/`)
Para cada aplicación (AS400, DB2, JDE, POS, Outlook, Teams, SharePoint, Exchange Online, OneDrive...):

| Subcarpeta | `tipo` | Pregunta clave |
|---|---|---|
| `01 - Modulos` | `modulo` | ¿Qué hace esta pantalla / módulo? |
| `02 - Procedimientos` | `procedimiento` | ¿Cómo se realiza el procedimiento? |
| `03 - Conceptos` | `concepto` | ¿Qué es este término o entidad? |
| `04 - Errores` | `error` | ¿Qué significa el error y cómo resolverlo? |
| `05 - SQL` | `sql` | ¿Qué información obtiene esta consulta? |
| `06 - Scripts` | `script` | ¿Qué automatiza este script? |
| `08 - Reglas de Negocio` | `regla` | ¿Qué condición o regla debe cumplirse? |
| `09 - Base de Conocimiento` | `caso` | ¿Cómo se resolvió el caso real reportado? |

### Desarrollo (`Desarrollo/<Proyecto>/`)
Proyectos propios de desarrollo (ej. Centro de Aplicaciones, Agente de Impresion POS, etc.).

### Carpetas Especiales
- `Soporte de Aplicaciones/00 - Inicio/`: Documentos normativos y mapa de navegación del vault.
- `Soporte de Aplicaciones/98 - Plantillas/`: Plantillas oficiales Markdown para cada tipo de nota.

---

## 3. Propiedades Obligatorias (Frontmatter YAML)

Toda nota debe comenzar con el bloque de propiedades:

```yaml
---
tipo: concepto       # concepto | modulo | procedimiento | regla | caso | error | script | sql
estado: Activo       # Activo | En revisión | Obsoleto | Borrador
nivel: Intermedio    # Básico | Intermedio | Avanzado
autor: Leonel
fecha_creacion: YYYY-MM-DD
ultima_revision: YYYY-MM-DD
---
```

> **Importante**: Al actualizar una nota existente, siempre debe actualizarse la fecha en `ultima_revision`.

---

## 4. Convenciones de Nomenclatura

- **Conceptos**: Nombre oficial (ej. `Orden de Compra.md`, `Sesión 5250.md`).
- **Módulos**: Código de la aplicación/pantalla (ej. `P4210.md`, `WRKACTJOB.md`).
- **Procedimientos**: Verbo en infinitivo (ej. `Reindexar catálogo de precios.md`, `Liberar cola de impresión.md`).
- **Casos reales**: Perspectiva y síntoma del usuario (ej. `Factura duplicada por corte de red en POS.md`).
- **Reglas**: Redactadas en forma de afirmación (ej. `Todo pedido requiere límite de crédito activo.md`).

---

## 5. Enlaces y Relaciones

- Usar enlaces wiki estilo Obsidian: `[[Nombre de Nota]]`.
- Mantener enlaces bidireccionales: cuando la nota A enlaza a la nota B, actualizar la sección `## Relacionado con` de la nota B.
- No duplicar explicaciones: referenciar conceptos existentes en lugar de redefinirlos.

---

## 6. Restricciones y Bloques Protegidos

- **Waypoints**: No modificar el contenido generado automáticamente entre `%% Begin Waypoint %%` y `%% End Waypoint %%`.
- **Índices de Aplicación**: No modificar los archivos `00 - <App>` salvo al dar de alta una nueva aplicación oficial.

---

## Relacionado con
- [[plantilla-concepto]]
- [[plantilla-modulo]]
- [[plantilla-procedimiento]]
- [[plantilla-regla]]
- [[plantilla-caso]]
- [[plantilla-error]]
- [[plantilla-script]]
- [[plantilla-sql]]

## Lo que aún no sé
- Ninguno por el momento.
