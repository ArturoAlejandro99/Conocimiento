[[Kubernetes]]

## Minikube
Iniciando minikube
```
minikube start --driver=podman
```
Es posible utilizar el comando -p para especificar el perfil


Para minikube
```
minikube stop
```
Es posible utilizar el comando -p para especificar el perfil


Eliminar minikube
```
minikube delete
```


Verificar listados de clusters
```
minikube profile list
```


En caso de contar con varios clusters se puede verificar cual es el que se modificara como el comando anterior en la columna Active, para cambiar de cluster es necesario ejecutar el comando
```
minikube profile <nombre del profile>
```


Version
```
minikube version
```


Validar ip de los nodos
```
minikube node list
```


Status
```
minikube status
```

---

## Cluster

Validar versión de kubectl
```
kubectl version --client**
```

Validar configuración de kubectl
```
kubectl config view
```

Validar información del cluster
```
kubectl cluster-info
```

Validar URL del proxy y levanta el proxy
```
kubctl proxy
```
---

## Namespace

Listar todos los namespaces
```
kubectl get namespaces
```

Crear un nuevo namespace
```
kubectl create namespace new-namespace-name
```
---

## Pods

Comando para crear un pod con el manifiesto en YAML
```
kubectl create -f def-pod.yaml
```
---
Comando para ejecutar un pod sin manifiesto
```
kubectl run nginx-pod --image=nginx:1.22.1 --port=80
```
---
Creación de una plantilla yaml
```
kubectl run nginx-pod --image=nginx:1.22.1 --port=80 \
--dry-run=client -o yaml > nginx-pod.yaml

kubectl run nginx-pod --image=nginx:1.22.1 --port=80 \
--dry-run=client -o json > nginx-pod.json
```
---
Actualiza o crea un pod con manifiesto
```
kubectl apply -f nginx-pod.yaml
```
---
Obtener pods
```
kubectl get pods
```
---
Obtener el manifiesto de un pod en formato yaml
```
kubectl get pod nginx-pod -o yaml
```
---
Obtener la descripción de un pod (estado, manifiesto, métricas, etc)
```
kubectl describe pod nginx-pod
```
---
Eliminar un pod
```
kubectl delete pod nginx-pod
```
---

## ReplicaSets

Creación o actualización de replicaSet
```
kubectl apply -f redis-rs.yaml
```
---
Obtención de replicasets
```
kubectl get rs
```
---
Modificación de replicaSet
```
kubectl scale rs frontend --replicas=4
```
---
Obtención de manifiesto
```
kubectl get rs frontend -o yaml
```
---
Obtención de descripción de replicaset
```
kubectl describe rs frontend
```
---
Eliminación de replicaSet
```
kubectl delete rs frontend
```
---
