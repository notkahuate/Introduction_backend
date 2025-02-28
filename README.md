## Documentación de la Base de Datos - Concesionario de Vehículos

## 📌 Introducción

Esta documentación describe el diseño de la base de datos para un concesionario de vehículos. La base de datos permite gestionar información sobre los vehículos en stock, clientes, ventas, servicios de mantenimiento y comisiones de los vendedores.

## 🎯 Objetivos del Diseño

Almacenar y gestionar información sobre vehículos disponibles y vendidos.

Administrar las ventas realizadas, los clientes y los vendedores.

Gestionar los servicios de mantenimiento realizados en los vehículos.

Registrar las comisiones generadas por los vendedores en cada venta.

Mantener la integridad y normalización de los datos.

## 🏗️ Estructura de la Base de Datos

🔹 Vehículos

Identificado por un VIN único.

Atributos: Marca, Modelo, Año, Precio, Color, Tipo de Combustible, Tipo de Transmisión, Estado.

Relación con ventas y mantenimientos.

🔹 Clientes

Identificados por un ID único.

Atributos: Nombre, Teléfono, Correo Electrónico (único), Dirección.

Puede comprar varios vehículos y solicitar servicios de mantenimiento.

🔹 Vendedores

Identificados por un ID único.

Atributos: Nombre, Número de Empleado (único), Fecha de Contratación.

Puede realizar múltiples ventas.

🔹 Ventas

Identificadas por un ID único.

Relacionadas con un cliente, un vendedor y un método de pago.

Registra Fecha, Total de la transacción.

🔹 Métodos de Pago

Identificados por un ID único.

Contiene tipos de pago disponibles (Tarjeta, Transferencia, Efectivo, etc.).

🔹 Detalle de Venta

Tabla intermedia que vincula ventas con vehículos vendidos.

Registra el precio de venta de cada vehículo.

🔹 Comisiones

Registra la comisión de cada venta.

Contiene el porcentaje de comisión y el monto calculado.

🔹 Servicios de Mantenimiento

Lista de servicios disponibles como mantenimiento preventivo o correctivo.

🔹 Mantenimiento

Se registran mantenimientos de vehículos (vendidos o no).

Puede estar asociado a un cliente o solo al concesionario.

🔹 Detalle de Mantenimiento

Tabla intermedia que vincula mantenimientos con servicios realizados.

Registra el costo de cada servicio.

🔹 Tipos de Combustible y Transmisión

Tablas separadas para mantener la normalización.

## 📌 Diagrama UML E-R

Notion: https://meteor-braid-1d4.notion.site/Campuscar-1a8ba10c6632803cb87ee29070afe0f7

Mermaid: https://www.mermaidchart.com/app/projects/72d3f443-b58d-4a02-91b5-0f3e0610d075/diagrams/60c9d369-71a6-4fb9-8c70-2e4a83ad799c/version/v0.1/edit

## 🔒 Restricciones y Validaciones

✅ Claves Primarias: ID autoincremental en todas las tablas.✅ Claves Foráneas: Garantizan la integridad referencial.✅ Restricciones de Unicidad: VIN de los vehículos y correo de los clientes deben ser únicos.✅ Estado del Vehículo: Un vehículo vendido cambia su estado a "No Disponible".

## ⚡ SQL Script

Se proporciona un script SQL con la estructura de la base de datos, incluyendo la creación de tablas, relaciones y restricciones.
Notion: https://meteor-braid-1d4.notion.site/Campuscar-1a8ba10c6632803cb87ee29070afe0f7

## 📢 Conclusión

Este diseño garantiza una gestión eficiente y organizada de la información en el concesionario. La estructura está normalizada para evitar redundancias y mejorar la integridad de los datos.

