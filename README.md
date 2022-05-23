# Proyecto ScaleApp Tronex SAS - DS4A
---
### Contacto 
  + Johny Vallejo Sánchez (johnyvallejo@tronex.com)
  + Andrés Franco Correa (afranco@tronex.com)

---

## Tablas

A continuación se detallan las tablas del conjunto de datos.

### 1. Customers

Tabla con información de los clientes.

+ Zona: Zona de venta Tronex (STRING)
+ ID rutero: Identificación interna única del cliente (STRING)
+ Cédula/NIT: (STRING)
+ Nombre del cliente: (STRING)
+ Nombre del negocio: (STRING)
+ Teléfono: Teléfono del cliente: (STRING)
+ Orden en el rutero: Orden de la visita: (STRING)
+ Dirección: Dirección del cliente: (STRING)
+ Ciudad: Ciudad del cliente: (STRING)

Esas serían las columnas reelevantes para el reto propuesto, las otras se pueden omitir.

### 2. sales2018

Tabla con información transaccional de los clientes a nivel de cliente-factura/sku desde el 2018.

+ Cédula/NIT (STRING)
+ Factura: identificador único de factura. Las que empiezan con NC son notas crédito (STRING)
+ Fecha de la factura: fecha de emisión de la factura (DATETIME)
+ SKU: código del producto vendido (STRING)
+ Descripción producto: Nombre del producto (STRING)
+ Fecha venta: fecha de la venta (DATETIME)
+ Venta cantidad: Número de unidades vendidas (FLOAT)
+ Venta pesos: Venta en pesos sin IVA del producto (FLOAT)
