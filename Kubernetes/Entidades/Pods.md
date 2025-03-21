[[Entidades]]
Es el objeto más pequeño en kubernetes. Representa una sola instancia de la aplicación. Un pod es la colección de uno o más contenedores.

A continuación se muestra una imagen de el formato de configuración de un pod en YAML.

```
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    run: nginx-pod
spec:
  containers:
  - name: nginx-pod
    image: nginx:1.22.1
    ports:
    - containerPort: 80
```

El contenido de la sección de spec es evaluado con propocitos de programación. Despues el kubelet del nodo seleccionado es el encargado de ejecutar la imagen con la ayuda del container runtime del nodo. 