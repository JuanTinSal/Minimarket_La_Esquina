### 2. Archivo `REGISTRO.md`

Tabla completada con el registro detallado para la **Fase 1** (puedes continuar completando las siguientes filas conforme avances):

```markdown
# Registro de Interacción con la IA

| Fase | Qué generó la IA | Qué corregí o rechacé | Por qué |
| --- | --- | --- | --- |
| **Fase 1** | Generó la estructura completa del documento base `D0.md` incluyendo descripción del problema, objetivos, requisitos funcionales (RF1–RF4), reglas de negocio (RN1–RN5), supuestos y limitaciones fuera de alcance. | Se revisó que la IA no incluyera módulos fuera de alcance (como login o roles) ni generara archivos de código/base de datos antes de tiempo. Se ajustó el formato de los supuestos para que utilicen explícitamente la etiqueta `SUPUESTO:`. | Para asegurar el cumplimiento estricto del alcance del caso del minimarket «La Esquina» y mantener la trazabilidad requerida en las instrucciones. |

### 2. Actualización de `REGISTRO.md`

Añade la siguiente fila a tu tabla existente en `REGISTRO.md`:

```markdown
| **Fase 2** | Generó los documentos `requirements.md` (con criterios EARS para RF1–RF4, RNF y trazabilidad de RN1–RN5) y `design.md` (arquitectura de 5 capas: Model, Repository, Service, Controller, Views, modelo ER en SQL, contratos de clases PHP 8 tipados y manejo de transacciones con bloqueo pesimista). | Se revisaron y solicitaron 2 correcciones propuestas antes de escribir código: 1) Agregar manejo explícito de concurrencia mediante `FOR UPDATE` en la transacción para evitar condiciones de carrera, y 2) Incluir el campo `precio_unitario` en la tabla `venta` para conservar el precio histórico del producto al momento del registro. | Garantizar la integridad transaccional en ventas simultáneas (RN5) e impedir que futuros cambios de precios en la tabla `producto` alteren el historial o reporte de ventas del día (RF4). |


### 2. Actualización de `REGISTRO.md`

Añade la siguiente fila a tu tabla en `REGISTRO.md`:

```markdown
| **Fase 3** | Generó los archivos de base de datos (`database/schema.sql`, `database/seed.sql`), las variables de entorno (`.env`, `.env.example`) y la regla de exclusión en `.gitignore`. Se definió la base de datos `bodega_ventas` (utf8mb4, InnoDB) con restricciones `PRIMARY KEY`, `FOREIGN KEY`, `UNIQUE` y `CHECK` para precios y stock, además del insert con los 8 productos iniciales. | Se verificó que `schema.sql` utilizara `DECIMAL(10,2)` en lugar de `FLOAT` para montos de dinero y que `seed.sql` usara `INSERT IGNORE` o una carga limpia para evitar errores por duplicación de claves únicas al reejecutar el script en phpMyAdmin. | Evitar fallos de precisión flotante en cálculos monetarios de ventas y prevenir errores de restricción `UNIQUE` en el campo `codigo` al probar el script repetidamente. |
