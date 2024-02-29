# Relación de cobranza

Controlador: **PaymentsController**

Ruta para acceder al filtro de relación de cobranza: /payments_relations
- En esta ruta se revisa el rol del usuario, si el rol es vendedor solo podra filtrar por fecha y cliente, de ser administrador podrá filtrar por fecha, cliente y vendedor.

Ruta para acceder a la relación de cobranza: **GET** /payments_relations/handler/{salesperson_no}/{customer_no}/{date_from}/{date_to}

- Esta ruta recibe los parametros de filtro como número de vendedor, número de cliente, fecha desde y fecha hasta.

Ruta para ver descargar el pdf de relación de cobranza: **GET** /payment/pdf/relation/{salesperson_no}/{customer_no}/{date_from}/{date_to}


![[payment-tables.png]]