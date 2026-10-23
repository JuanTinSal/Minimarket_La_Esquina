# FASE 1 — DOCUMENTO BASE D0.md
## Sistema de Ventas e Inventario del Minimarket «La Esquina»

Actúa como analista de sistemas y tutor de un estudiante de Ingeniería de Sistemas. Estoy desarrollando un examen individual del curso Inteligencia Artificial y Sistemas Expertos.

Tu tarea es analizar el caso proporcionado y elaborar el archivo `D0.md` en la raíz del proyecto.

IMPORTANTE:
- Antes de crear o modificar archivos, revisa la estructura del proyecto.
- Si `D0.md` ya existe, léelo y mejóralo sin eliminar información válida.
- No generes todavía código PHP, scripts SQL ni otros documentos de fases posteriores.
- No inventes funcionalidades que no aparecen en el caso.

## 1. Caso del negocio

El minimarket ficticio «La Esquina», ubicado en San Vicente de Cañete, vende abarrotes, lácteos, bebidas, conservas y productos de limpieza.

Actualmente, registra las ventas en un cuaderno y controla el inventario revisando visualmente los estantes. Por este motivo, el dueño desconoce cuánto vendió al finalizar el día y en ocasiones se queda sin productos de alta rotación porque no detecta oportunamente que el stock está disminuyendo.

Se necesita una aplicación web interna utilizada por el cajero para gestionar productos, consultar el inventario y registrar ventas.

## 2. Funcionalidades requeridas

RF1. Registrar productos con código, nombre, categoría, precio de venta, stock actual y stock mínimo.

RF2. Listar los productos y resaltar aquellos cuyo stock actual sea menor o igual al stock mínimo.

RF3. Registrar la venta de un producto seleccionado por el cajero, indicando la cantidad. El sistema debe tomar el precio vigente, calcular el total, registrar la fecha y hora y descontar el stock.

RF4. Listar las ventas del día y mostrar el total vendido durante esa fecha.

RF1, RF2 y RF3 son obligatorios para aprobar. RF4 permite completar la puntuación máxima del criterio de código.

## 3. Reglas de negocio

RN1. La cantidad vendida debe ser mayor que cero.

RN2. No se puede vender una cantidad superior al stock disponible.

RN3. El precio de venta no puede ser negativo.

RN4. El código de producto debe ser único.

RN5. El registro de la venta y el descuento del stock deben ejecutarse conjuntamente: ambas operaciones se confirman o ninguna queda aplicada.

## 4. Datos de prueba

Los siguientes productos deben conservarse exactamente para las fases posteriores:

| Código | Nombre | Categoría | Precio S/ | Stock | Mínimo |
|---|---|---|---:|---:|---:|
| P001 | Arroz superior 5 kg | Abarrotes | 22.50 | 20 | 5 |
| P002 | Azúcar rubia 1 kg | Abarrotes | 4.20 | 30 | 10 |
| P003 | Aceite vegetal 1 L | Abarrotes | 9.90 | 12 | 4 |
| P004 | Leche evaporada 400 g | Lácteos | 4.00 | 48 | 12 |
| P005 | Fideo spaghetti 500 g | Abarrotes | 3.50 | 25 | 8 |
| P006 | Atún en trozos 170 g | Conservas | 6.50 | 3 | 6 |
| P007 | Gaseosa 1.5 L | Bebidas | 7.00 | 18 | 6 |
| P008 | Detergente 1 kg | Limpieza | 11.80 | 2 | 4 |

P006 y P008 deben identificarse inicialmente como productos con stock bajo.

## 5. Contenido obligatorio de D0.md

Organiza el documento con estas secciones:

1. Nombre y descripción del sistema.
2. Problema principal expresado en una sola frase.
3. Objetivo general.
4. Usuarios y responsabilidades: cajero y dueño, sin inventar permisos adicionales.
5. Descripción del proceso actual y sus dificultades.
6. Requisitos funcionales RF1–RF4.
7. Requisitos no funcionales relacionados con seguridad e integridad de los datos.
8. Reglas de negocio RN1–RN5.
9. Elementos fuera de alcance.
10. Supuestos identificados explícitamente con la palabra SUPUESTO.

Fuera de alcance:
- Inicio de sesión.
- Gestión de roles.
- Clientes.
- Facturación electrónica.
- Agentes conversacionales.
- Despliegue público.

Los supuestos deben corresponder únicamente a aspectos no especificados en el caso. No los presentes como requisitos confirmados.

## 6. Calidad del documento

- Redacta en español claro, formal y comprensible.
- Utiliza tablas y listas cuando faciliten la lectura.
- Evita repeticiones y requisitos ambiguos.
- Mantén trazabilidad entre el problema, las funcionalidades y las reglas de negocio.
- No agregues módulos que no se solicitan.
- No generes todavía requirements.md, design.md, schema.sql, seed.sql ni archivos PHP.

## 7. Verificación final

Antes de finalizar, comprueba que:
- Los cuatro requisitos funcionales estén documentados.
- Las cinco reglas de negocio estén completas.
- Los usuarios y el proceso actual estén descritos.
- Los elementos fuera de alcance estén identificados.
- Los supuestos estén claramente diferenciados de los requisitos.

Guarda el resultado en `D0.md` en la raíz del proyecto.

Al terminar, explícame brevemente qué contiene el archivo y qué aspectos debería revisar como estudiante. No continúes con la Fase 2 hasta recibir mi autorización.

# FASE 2 — ESPECIFICACIÓN Y DISEÑO
## Proyecto: Minimarket «La Esquina»

Actúa como analista de requisitos y arquitecto de software. Continúa el proyecto del examen individual de Inteligencia Artificial y Sistemas Expertos.

Debes crear los archivos `requirements.md` y `design.md` en la raíz del proyecto, utilizando como fuente principal el documento `D0.md`.

IMPORTANTE:
- Lee primero `D0.md` y revisa la estructura actual del proyecto.
- Conserva las decisiones válidas de la Fase 1.
- No programes todavía la aplicación.
- No ejecutes tareas automáticas de `tasks.md`, aunque Kiro o el agente las genere.
- No generes todavía código PHP ni scripts SQL.
- Si encuentras contradicciones entre los requisitos y el caso, explícalas antes de resolverlas.

# PARTE A. requirements.md

## 1. Criterios de aceptación en formato EARS

Redacta criterios de aceptación utilizando una estructura verificable como:

«CUANDO [condición], EL SISTEMA DEBERÁ [resultado esperado]».

Identifica cada criterio mediante los códigos RF y RNF correspondientes.

Incluye los cuatro requisitos funcionales:

- RF1: registro de productos.
- RF2: listado de productos y resaltado de stock bajo.
- RF3: registro de ventas con cálculo del total, fecha, hora y descuento de stock.
- RF4: consulta de ventas del día y total vendido.

Incluye también los requisitos no funcionales de seguridad e integridad de datos definidos en D0.md.

## 2. Trazabilidad de las reglas de negocio

Debes incluir las cinco reglas de negocio de D0.md:

- RN1: cantidad vendida mayor que cero.
- RN2: cantidad vendida no superior al stock disponible.
- RN3: precio no negativo.
- RN4: código de producto único.
- RN5: venta y descuento de stock como operación atómica.

Cada regla RN debe aparecer en al menos un criterio de aceptación verificable.

Utiliza identificadores consistentes y señala qué requisito funcional se relaciona con cada regla.

Los criterios deben describir condiciones y resultados comprobables, no frases vagas como «el sistema funciona correctamente».

# PARTE B. design.md

## 1. Arquitectura de cinco capas

Describe las siguientes capas, respetando el orden solicitado:

Model → Repository → Service → Controller → Views.

Para cada capa, explica:

- Responsabilidad principal.
- Qué operaciones realiza.
- Qué operaciones NO debe realizar.
- Cómo se relaciona con las otras capas.

Responsabilidades esperadas:

Model:
Representa las entidades Producto y Venta y sus datos.

Repository:
Realiza consultas y operaciones SQL mediante PDO preparado. No contiene reglas de negocio.

Service:
Implementa las reglas de negocio y coordina las operaciones. La venta y el descuento de stock deben realizarse mediante una transacción atómica.

Controller:
Recibe las solicitudes, invoca los servicios y determina la respuesta apropiada. No debe contener reglas de negocio complejas.

Views:
Presenta formularios, listados y mensajes. No ejecuta consultas SQL ni decide si una venta es válida.

Explica claramente los límites de cada capa y evita duplicar responsabilidades.

## 2. Diseño de la base de datos

Define las tablas principales `producto` y `venta`.

Para cada tabla, especifica:
- Nombre del campo.
- Tipo de dato SQL.
- Clave primaria o foránea, cuando corresponda.
- Restricciones.
- Finalidad del campo.

La tabla producto debe contemplar:
- Identificador del producto.
- Código único.
- Nombre.
- Categoría.
- Precio de venta.
- Stock actual.
- Stock mínimo.

La tabla venta debe contemplar:
- Identificador de la venta.
- Referencia al producto vendido.
- Cantidad.
- Precio unitario aplicado a la venta.
- Total de la venta.
- Fecha y hora.

Define las claves y restricciones necesarias:
- PRIMARY KEY.
- FOREIGN KEY.
- UNIQUE para el código del producto.
- CHECK para precio no negativo, stock no negativo y cantidad mayor que cero.

Utiliza tipos apropiados para precios monetarios, cantidades y fechas. Justifica brevemente las decisiones.

La estructura debe ser coherente con los ocho productos de prueba de D0.md. No cambies sus códigos, nombres, categorías, precios, stocks ni mínimos.

Explica cómo se conserva el precio vigente utilizado en una venta y cómo se mantiene la relación entre producto y venta.

## 3. Contratos de clases con firmas tipadas

Propón las clases y sus contratos principales para las cinco capas.

Incluye las firmas de los métodos más importantes, con:
- Nombre de clase y método.
- Parámetros tipados.
- Tipo de retorno.
- Excepciones relevantes.
- Responsabilidad del método.

Considera, como mínimo:
- Registro y consulta de productos.
- Consulta de productos con stock bajo.
- Registro de ventas.
- Consulta de ventas del día.
- Obtención de productos por identificador.
- Persistencia mediante repositorios.

Utiliza sintaxis compatible con PHP 8 y nombres coherentes con la arquitectura.

Las firmas son contratos de diseño, no implementaciones completas. No generes todavía los archivos PHP.

## 4. Transacción de venta y manejo de errores

Describe paso a paso cómo registrar una venta:

1. Recibir el producto y la cantidad solicitada.
2. Validar que el producto exista.
3. Validar que la cantidad sea mayor que cero.
4. Comprobar el precio y el stock disponible.
5. Iniciar la transacción.
6. Registrar la venta utilizando el precio vigente.
7. Descontar el stock sin permitir que quede negativo.
8. Confirmar ambas operaciones mediante COMMIT.
9. Si ocurre un error, ejecutar ROLLBACK y propagar una excepción controlada.

Asegúrate de que el diseño contemple la concurrencia: dos operaciones simultáneas no deben vender unidades que ya no están disponibles.

Explica cómo se distinguen los registros inexistentes de los errores de base de datos y cómo se comunican los errores sin exponer detalles internos al usuario.

## 5. Seguridad y restricciones técnicas

El diseño debe ser compatible con los requisitos del examen:

- PHP 8 orientado a objetos.
- MySQL/MariaDB de XAMPP.
- PDO con sentencias preparadas.
- Sin frameworks.
- Credenciales almacenadas en variables de entorno.
- Salida HTML escapada.
- Protección CSRF en formularios.
- Manejo controlado de excepciones.
- Una clase por archivo, namespaces App\ y declare(strict_types=1).
- Reglas de negocio ubicadas en Service.

No introduzcas inicio de sesión, roles, clientes, facturación electrónica, agentes conversacionales ni despliegue público.

# PARTE C. REVISIÓN Y CORRECCIONES

Antes de terminar:

1. Verifica que cada regla RN de D0.md esté representada en al menos un criterio de aceptación de requirements.md.
2. Verifica que las cinco capas estén descritas y que sus responsabilidades no se mezclen.
3. Comprueba que las tablas y los tipos sean coherentes con los ocho productos de prueba.
4. Comprueba que las firmas de los métodos tengan tipos de parámetros y retorno.
5. Comprueba que la transacción y el manejo de errores estén documentados.
6. Identifica cualquier contradicción o decisión que requiera confirmación.

Propón al menos dos mejoras concretas a tu primer borrador. Explica por qué son necesarias y espera mi revisión antes de aplicarlas.

No inventes que el estudiante realizó correcciones manuales. Explica las propuestas para que yo pueda revisarlas, decidir si las acepto y registrar las correcciones reales en REGISTRO.md.

# RESULTADO ESPERADO

Crear:
- `requirements.md`
- `design.md`

Si `REGISTRO.md` no existe, indícalo; no inventes un historial de decisiones realizadas.

Al finalizar, presenta una lista breve de verificación de los requisitos cumplidos, las dos correcciones propuestas y cualquier pendiente. No ejecutes tareas de implementación ni generes código PHP o SQL hasta recibir mi autorización.
