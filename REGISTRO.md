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

### 2. Actualización de `REGISTRO.md`

Añade la siguiente fila a tu tabla en `REGISTRO.md`:

```markdown
| **Fase 4** | **P1:** Definió las decisiones técnicas (PHP 8 strict_types, arquitectura en 5 capas, PDO preparado) y el árbol de directorios.<br>**P2:** Implementó progresivamente la arquitectura: configuración PDO (`config/database.php`), Modelos (`Producto`, `Venta`), Repositorios (`ProductoRepository`, `VentaRepository`), Servicios (`ProductoService`, `VentaService`), Controladores, Vistas y `public/index.php` con protección CSRF y prevención XSS (`htmlspecialchars`).<br>**P3:** Creó el script ejecutable `tests/run.php` usando repositorios falsos en memoria para validar las 6 reglas de negocio clave sin depender de la BD. | Se ajustó la transacción en `VentaService` para asegurar que el aislamiento transaccional maneje adecuadamente los bloques `try-catch` y la reconexión PDO. Además, se corrigió el escape en la vista de productos para evitar errores de renderizado en caracteres especiales de nombres y categorías. | Garantizar que la lógica de negocio se valide de forma aislada e independiente en la suite de pruebas `tests/run.php` y asegurar un entorno seguro frente a vulnerabilidades de seguridad web (XSS/CSRF). |

### 2. Actualización de `REGISTRO.md`

Añade la siguiente fila a tu tabla en `REGISTRO.md`:

```markdown
| **Fase 5** | **P4:** Realizó una auditoría de seguridad OWASP Top 10 analizando inyección SQL, XSS, CSRF, exposición de credenciales, manejo de excepciones e integridad en transacciones.<br>**P5:** Documentó la deuda técnica en `TECH_DEBT.md` (identificando 3 atajos: ausencia de autenticación/roles, falta de paginación en reportes y repositorio en memoria simplificado), redactó el `README.md` con instrucciones de instalación/pruebas y verificó `.gitignore`. | Se confirmó la adición de la validación estricta de tokens CSRF en las peticiones POST y el escape dinámico en las vistas. Además, se verificó que `.env` permaneciera totalmente excluido del control de versiones mediante `git check-ignore`. | Cumplir con los estándares mínimos de seguridad web, evitar fugas de información confidencial en el repositorio de Git y brindar documentación clara para la ejecución y mantenimiento del proyecto. |
