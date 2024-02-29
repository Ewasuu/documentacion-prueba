# Sincronizador (belt-g)

Aplicación de consola en c# que conecta con el servicio de azure service bus. Recibe mensajes con un codigo que luego le pasamos a un objeto factory y nos retorna un repositorio de el tipo de objeto que se va a crear, actualizar o eliminar.

Todos los repositorios implementan la interfaz IMessageRepository que consta de un solo metodo:

```c#
public void ExecuteAction(string json, string key);
```

Desde metodo se maneja la logica de la sincronizacion. En el key irá un valor *save* o *delete*.
