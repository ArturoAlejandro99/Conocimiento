[[Entidades]]
Este objeto sirve para replicar pods. Cuando se tiene una sola instancia de un pod ocurre el riesgo de que se rompa, por lo que se opta tener varias copias del mismo pod ejecutandose en paralelo.

Un replicaSet de un mismo pod son identicos a excepción del nombre e IP.
![[Pasted image 20250320125056.png]]

A continuación un ejemplo de un manifiesto de una replicaSet.
```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: guestbook
    tier: frontend
spec:
  replicas: 3
  selector:
    matchLabels:
      app: guestbook
  template:
    metadata:
      labels:
        app: guestbook
    spec:
      containers:
      - name: php-redis
        image: gcr.io/google_samples/gb-frontend:v3
```

