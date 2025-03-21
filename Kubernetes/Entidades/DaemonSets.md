Son operadores para manejar los agentes de los nodos. Son parecidos a los deployments y replicasets con la única diferencia de que estos obligar a poner un solo pod en cada nodo.

DaemonSets son utilizados para monitorear información de todos los nodos o ejecutar almacenes, redes o proxys en todos los nodos.

Un ejemplo de esto es el kube-proxy.

Si un nodo falla o se remueve del cluster, el daemonSets opera como recolector de basura de los pods. Si se elimina un DaemonSets todas las replicas de pod se eliminan también.

Los daemonSets son aún regidos por el Scheduler por lo que solo se podrán crear pods en los nodos que tengan los recursos suficientes.

A continuación un ejemplo de un daemonSets.

```
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: fluentd-agent
  namespace: default
  labels:
    k8s-app: fluentd-agent
spec:
  selector:
    matchLabels:
      k8s-app: fluentd-agent
  template:
    metadata:
      labels:
        k8s-app: fluentd-agent
    spec:
      containers:
      - name: fluentd
        image: quay.io/fluentd_elasticsearch/fluentd:v4.5.2
```
