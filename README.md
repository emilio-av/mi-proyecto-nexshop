# 🛒 Proyecto NexShop Grupo SA

Diseño e implementación de una base de datos relacional para NexShop Group SA.

Bienvenido al repositorio oficial del proyecto final de bases de datos para NexShop Group SA. El proyecto desarrolla una base de datos para gestionar una empresa con tienda online y tiendas físicas.

---

# 👤 Información del Alumno

- **Nombre:** Emilio Anaya Verdugo
- **Curso:** 2º SMR 
- **GitHub:** https://github.com/emilio-av

---

# 🏢 Descripción de la Empresa

NexShop Group SA es una empresa dedicada al comercio minorista que combina una plataforma de venta online con varias tiendas físicas. La base de datos permite gestionar productos, clientes, proveedores, empleados, pedidos, ventas, envíos y devoluciones.

---

# 📊 Diagrama Entidad-Relación

```mermaid
erDiagram
    sede ||--o{ empleado : tiene
    categoria ||--o{ subcategoria : contiene
    subcategoria ||--o{ producto : clasifica
    producto ||--o{ historial_precio : tiene
    empleado ||--o{ proveedor : representa
    producto ||--o{ producto_proveedor : suministrado
    proveedor ||--o{ producto_proveedor : suministra

    cliente ||--o{ direccion_cliente : tiene
    cliente ||--o{ pedido_online : realiza
    direccion_cliente ||--o{ pedido_online : entrega
    pedido_online ||--o{ linea_pedido : contiene
    producto ||--o{ linea_pedido : vendido

    pedido_online ||--o{ envio : genera
    sede ||--o{ envio : origen
    envio ||--o{ linea_envio : incluye
    linea_pedido ||--o{ linea_envio : envia

    sede ||--o{ venta_presencial : realiza
    empleado ||--o{ venta_presencial : atiende
    cliente ||--o{ venta_presencial : compra
    venta_presencial ||--o{ linea_venta : contiene
    producto ||--o{ linea_venta : vendido

    venta_presencial ||--o{ devolucion_presencial : devuelve
    devolucion_presencial ||--o{ linea_devolucion : contiene
    linea_venta ||--o{ linea_devolucion : corresponde

    producto ||--o{ stock : tiene
    sede ||--o{ stock : almacena

    producto ||--o{ transferencia_stock : mueve
    sede ||--o{ transferencia_stock : origen_destino
    empleado ||--o{ transferencia_stock : autoriza

    producto ||--o{ promocion : tiene
    cliente ||--o{ ticket_incidencia : abre
    pedido_online ||--o{ ticket_incidencia : relacionado
    empleado ||--o{ ticket_incidencia : gestiona

    cliente ||--o{ valoracion : escribe
    producto ||--o{ valoracion : recibe

    cliente ||--o{ movimiento_puntos : acumula
    pedido_online ||--o{ movimiento_puntos : genera
```

---

# 📂 Estructura del Repositorio

```text
mi-proyecto-nexshop/
│── README.md
│
├── docs/
│   ├── memoria.md
│   └── modelo_relacional.md
│
├── sql/
│   ├── schema.sql
│   └── datos.sql
│
└── consultas/
    └── consultas.sql
```

---

# ⚙️ Cómo ejecutar

Crear la base de datos y ejecutar:

```bash
mysql -u root -p < sql/schema.sql
mysql -u root -p nexshop < sql/datos.sql
mysql -u root -p nexshop < consultas/consultas.sql
```

---

# 🛠 Tecnologías utilizadas

- MySQL 8
- SQL
- Git
- GitHub
- Laragon
- DBEAVER
