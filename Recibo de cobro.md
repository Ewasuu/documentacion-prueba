
# Recibo de cobro

Controlador: **PaymentsController**

Ruta de Listado: **GET** /payments
 - Obtiene todos los pagos registrados del vendedor autenticado, si el usuario autenticado tiene el rol de administrador retornara los pagos de todos los vendedores.

Ruta de vista de creación: **GET** /payments/{customer_no}
 - Recibe el número del cliente del recibo, luego obtiene el numero del vendedor que tiene ese cliente asignado para crear el código del recibo.

Antes de pasar a esta ruta se debe colocar en el local storage los datos necesarios en el siguiente formato:

```json

[

    {

        "no": "492702",

        "price_usd": "250.81",

        "price_bs": "9087.57",

        "total_without_iva_bs": "7606.38",

        "total_without_iva_usd": "209.93",

        "exchange_amount": "36.2329"

    },

    {

        "no": "492701",

        "price_usd": "679.89",

        "price_bs": "24634.39",

        "total_without_iva_bs": "20617.25",

        "total_without_iva_usd": "569.02",

        "exchange_amount": "36.2329"

    }

]

```

Ruta de creación: **GET** /payments/save

Esta ruta recibe el siguiente BODY:

```json
{

    "customer_no": "CUST12345",

    "salesperson_no": "SALES12345",

    "observation": "Observación de prueba",

    "base_bs": 1000.00,

    "base_usd": 200.00,

    "total_bs": 1500.00,

    "total_usd": 300.00,

    "discount_bs": 100.00,

    "discount_usd": 20.00,

    "retained_amount_bs": 200.00,

    "retained_amount_usd": 40.00,

    "devolution_amount_bs": 50.00,

    "devolution_amount_usd": 10.00,

    "exchange_amount": 5.00,

    "invoices": [

        {

            "no": "INV123",

            "amount_bs": 500.00,

            "amount_usd": 100.00

        }

    ],

    "payments": [

        {

            "no": "PAY123",

            "bankId": "01",

            "date": "2024-02-21",

            "amount_bs": 250.00,

            "amount_usd": 50.00,

            "exchange_amount": 2.50

        }

    ]

}

```

Ruta de vista de actualización: **GET** /payment/edit/{id}
- En esta ruta se manda el id para luego obtener los datos del recibo atraves de la vista mediante una api.

Ruta para obtener datos de un recibo ya creado: **GET** /payments/{id}
- Retorna todos las datos guardados en el recibo con el id colocado como las facturas y los cobros.

Ruta para editar un recibo: **PUT** /payments/{id}

Esta ruta recibe el siguiente BODY:

```json
{

    "observation": "Observación de prueba",

    "total_bs": 1500.00,

    "total_usd": 300.00,

    "discount_bs": 100.00,

    "discount_usd": 20.00,

    "retained_amount_bs": 200.00,

    "retained_amount_usd": 40.00,

    "payments": [

        {

            "no": "PAY123",

            "bankId": "01",

            "date": "2024-02-21",

            "amount_bs": 250.00,

            "amount_usd": 50.00,

            "exchange_amount": 2.50

        },

        {

            "no": "PAY124",

            "bankId": "02",

            "date": "2024-02-22",

            "amount_bs": 250.00,

            "amount_usd": 50.00,

            "exchange_amount": 2.50

        }

    ]

}

```

Ruta para ver el pdf del recibo: **GET** /payment/pdf/show/{id}
- Esta ruta recibe el id del cobro para buscar toda su informacion. Dentro del controlador se hacen las validaciones necesarias para revisar los permisos del usuario para acceder a este recurso


![[payment-tables.png]]