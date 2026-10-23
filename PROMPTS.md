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
