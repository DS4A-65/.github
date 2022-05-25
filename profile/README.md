# Proyecto ScaleApp Tronex SAS - DS4A
---
### Contacto 
  + Johny Vallejo Sánchez (johnyvallejo@tronex.com)
  + Andrés Franco Correa (afranco@tronex.com)

---

## Fuentes de datos

A continuación se detallan las tablas del conjunto de datos.

### 1. `Customers`

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

### 2. `sales2018`

Tabla con información transaccional de los clientes a nivel de cliente-factura/sku desde el 2018.

+ Cédula/NIT (STRING)
+ Factura: identificador único de factura. Las que empiezan con NC son notas crédito (STRING)
+ Fecha de la factura: fecha de emisión de la factura (DATETIME)
+ SKU: código del producto vendido (STRING)
+ Descripción producto: Nombre del producto (STRING)
+ Fecha venta: fecha de la venta (DATETIME)
+ Venta cantidad: Número de unidades vendidas (FLOAT)
+ Venta pesos: Venta en pesos sin IVA del producto (FLOAT)

---

## Población de control

La información de la población de control está contenida en la información transaccional aplicando las siguientes reglas y filtros sobre la misma:

1. Filtrar por los campos `Centro_Costos == "02"`, `Feha_Factura == "2022-02-28` y `Referencia` que empiecen con `LY`, e.g.
```json
{
  "CUSTRUTEROID" : "920190206013554",
  "Factura" : "HHBO0519419",
  "Fecha_Factura" : "2022-05-20T05:00:00.000Z",
  "Referencia" : "LYGUANT8AMX2",
  "Cantidad_Original" : 1.000000000000,
  "Monto_Venta_Pesos_Linea" : 2298.800000000000,
  "Centro_Costos" : "02"
}
```
3. El conjunto de datos filtrado contiene a los clientes *adoptantes*, identificados con `CUSTRUTEROID`, que compraron la nueva categoría.
4. La *población de control* serían los clientes *adoptantes* que están en el histórico transaccional (puede ser que algunos de los adoptantes no tengan un histórico transaccional) y tienen un comportamiento de compra de productos del portafolio de Tronex.
