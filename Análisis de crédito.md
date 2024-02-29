
# Análisis de credito

Controlador: **CreditAnalysisController**

Ruta de Listado: **GET** /clientanalysis
- Retorna todos los datos de los clientes. Si el rol del usuario autenticado es vendedor solo retornara los clientes de ese vendedor

Ruta de datos completos del cliente: **GET** /clientanalysis/{id}
- Se le pasa el id del cliente y retorna los datos para ser mostrados en un modal

Ruta del buscador de clientes: **GET** /clientanalysis/search/{key}
- Busca al cliente que tenga un dato que haga match con el valor colocado en el parametro {key}. Busca por nombre del cliente, numero del cliente, numero del vendedor y nombre del vendedor.

Ruta de análisis de credito de un cliente: **GET** /clientanalysis/show/{no}
- Retorna el análisis de credito del cliente colocado en el {no} de la ruta.


![[documents-tables.png]]