1:corralon 
1FN:**linea** (`nro_factura` PK, `producto` PK, `fecha`, `cuit`, `cliente`, `domicilio`, `precio`, `cantidad`);
elimine:`producto_1`, `precio_1`, `cant_1`, `producto_2`, `precio_2`, `cant_2` y nos nnulls.

2FN:**factura** (`nro_factura` PK, `fecha`, `cuit`, `cliente`, `domicilio`) **producto** (`producto` PK, `precio`) **linea** (`nro_factura` PK/FK, `producto` PK/FK, `cantidad`) 
elimine dependecias parciales de:* * (`nro_factura, producto)`:
    * `fecha`, `cuit`, `cliente` y `domicilio` dependían únicamente de `nro_factura`.
    * `precio` dependía únicamente de `producto`. y el precio dependia solo de producto

3FN: mis tablas:
**cliente** (`cuit` PK, `cliente`, `domicilio`) **factura** (`nro_factura` PK, `fecha`, `cuit` FK) **producto** (`producto` PK, `precio`) **linea** (`nro_factura` PK/FK, `producto` PK/FK, `cantidad`) y elimine : La dependencia transitiva en la tabla factura, donde cuit (atributo no clave) determinaba a cliente y domicilio (nro_factura $\rightarrow$ cuit $\rightarrow$ cliente, domicilio).
