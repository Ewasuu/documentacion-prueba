
# Cotizador

Ubicación: 
	- proyecto: belt-g-cloud
	- repositorio: belt-g-react

Es una aplicación en react que corre con el comando:

```
yarn start
```

Al levantarse la página se verá una pagina en blanco. Esta aplicación incia desde la ruta: 

> /cart/{base64}

La ruta mediante la que se accede puede ser como esta:

```
http://localhost:3000/cart/eyJ1c2VyX2lkIjoiYWRtaW5AaG90bWFpbC5jb20iLCJ2ZW5kb3Jfbm8iOiIxOCIsIm5hbWUiOiJNaWNoZWxsIFJpYm91IiwiY3VzdG9tZXJfbm8iOiI2MTAiLCJjdXN0b21lcl9pZCI6IjMiLCJjdXN0b21lcl9uYW1lIjoiRkVSUkVUQU5RVUUgUyB5ICBCT01CQVMgTEEgMjQsIEMuQS4iLCJkYXRlX2Zyb20iOiIyMDI0LTAyLTI3IiwiZGF0ZV90byI6IjIwMjQtMDItMjciLCJvcmRlcl90ZW1wX2lkIjo3NjE1LCJyb2xlIjoiYWRtaW4iLCJkZXNjcmlwdGlvbiI6IkFkbWluaXN0cmFkb3IgR2xvYmFsIn0=
```

Donde el base64 tiene los datos del vendedor y cliente de este pedido. Si se esta retomando un pedido anteriormente guardado entonces tendra en sus datos el id de ese pedido temporal para recuperar las lineas de ese pedido

Si intentas acceder a las rutas del cotizador sin pasar por este paso antes te retornara al aplicativo para poder hacer el proceso normal.

## Build

Se ejecuta con el comando:

```
yarn build
```

Deja una carpeta build con los archivos 

├── build/
│   ├── static/
│   ├── index.html
│   ├── manifest.json
│   ├── favicon.ico
│   ├── robots.txt
│   └── asset-manifest.json



En la carpeta index.html se copian los valores de la etiqueta script y la etiqueta link que seran de esta forma: 

```html
<script defer="defer" src="/static/js/main.47677157.js"></script<link href="/static/css/main.4141205d.css" rel="stylesheet">
```

Esos valores se pegan en el aplicativo de belt-g en un archivo llamado **cart.blade.php** ubicado en *resources/views/layouts/*
con la siguiente estructura:

```html
    <title>Grifocentro | ventas</title>
    <script defer="defer" src="/static/js/main.9435316b.js"></script>
    <link href="/static/css/main.4c100e99.css" rel="stylesheet" />
```

Estos valores son los que se van a cambiar del index.html de la build de react al archivo de cart.blade.php del aplicativo.

Luego de esto se colocan la carpeta *static/* dentro de la carpeta *public/* del aplicativo. 