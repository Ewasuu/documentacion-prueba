# Productos del cotizador

Ubicación: 
	- proyecto: belt-g-cloud
	- repositorio: belt-g-admin-app

Es una aplicación en react que corre con el comando:

```
yarn start
```

En esta aplicación las rutas empiezan con el prefijo *application/* seguido de la ruta que se busca.
Ejemplo:

```
http://localhost:3000/application/products
```

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
<script defer="defer" src="/static/js/main.47677157.js"></script>
<link href="/static/css/main.4141205d.css" rel="stylesheet">
```

Esos valores se pegan en el aplicativo de belt-g en un archivo llamado **product.blade.php** ubicado en *resources/views/layouts/*
con la siguiente estructura:

```html
    <title>Grifocentro | ventas</title>
    <script defer="defer" src="/products-react/static/js/main.e9cfc1fa.js"></script>
    <link href="/products-react/static/css/main.aa6a5f08.css" rel="stylesheet">
```

Estos valores son los que se van a cambiar del index.html de la build de react al archivo de product..blade.php del aplicativo añadiendole antes */products-react/*  que apunta hacia la carpeta donde se colocan los archivos estaticos de esta build.

Luego de esto se colocan la carpeta *static/* dentro de la carpeta *public/products-react* del aplicativo. 