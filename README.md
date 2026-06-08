Mini Proyecto NexShop — Base de Datos

Alumno: Emilio Anaya Verdugo

Proyecto de diseño e implementación de una base de datos relacional para NexShop Group S.A., empresa con tienda online y tres tiendas físicas. El modelo cubre catálogo, precios, promociones, proveedores, stock, pedidos online, ventas presenciales, envíos, devoluciones, incidencias, empleados, valoraciones y fidelización.

Estructura
```text
mi-proyecto-nexshop/
├── README.md
├── docs/
│   ├── memoria.md
│   └── modelo_relacional.md
├── sql/
│   ├── schema.sql
│   └── datos.sql
└── consultas/
    └── consultas.sql
```
Cómo ejecutar

Crear la base de datos en MySQL 8 o MariaDB compatible.
Ejecutar `sql/schema.sql`.
Ejecutar `sql/datos.sql`.
Ejecutar `consultas/consultas.sql` para probar las consultas obligatorias.
Ejemplo:
```bash
mysql -u root -p < sql/schema.sql
mysql -u root -p nexshop < sql/datos.sql
mysql -u root -p nexshop < consultas/consultas.sql
