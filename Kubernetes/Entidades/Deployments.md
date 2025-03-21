[[Entidades]]

Estos objetos proveen actualizaciones declarativas a pods y replicasets. Permite actualizaciones y rollbacks de manera interrumpida también conocida como la estrategia RollingUpdate.

A continuación un ejemplo de un manifiesto.

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
  labels:
    app: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx-deployment
  template:
    metadata:
      labels:
        app: nginx-deployment
    spec:
      containers:
      - name: nginx
        image: nginx:1.20.2
        ports:
        - containerPort: 80
```

