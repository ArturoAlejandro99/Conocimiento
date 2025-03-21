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

## Depoloyments

Obtención de deploys
```
kubectl get deployments
```

o para obtener información más detallada 
```
kubectl get deploy -o wide
```
---
Actualizar la cantidad de pods
```
kubectl scale deploy nginx-deployment --replicas=4
```
---
Descripción del deployment
```
kubectl describe deploy nginx-deployment
```
---
Para obtener visibilidad del estado de actualización del despliegue 
```
kubectl rollout status deploy nginx-deployment
```
---
Comando para obtener el histórico de revisiones
```
kubectl rollout history deploy nginx-deployment
```
para revisar alguna en especifico se utiliza
```
---revision=<numero de revisión>
```
---
Actualizar imagen del contenedor y registrar el cambio en el historico
```
kubectl set image deploy nginx-deployment nginx=nginx:1.21.5 --record
```
---
Obtener información del historico
```
kubectl rollout history deploy nginx-deployment --revision=2
```
---
Realizar rollback a una revisión especifica
```
kubectl rollout undo deploy nginx-deployment --to-revision=1
```
---
Eliminar todo un deploy
```
kubectl delete deploy nginx-deployment
```
---

## DaemonSets

Obtención de los daemonsets
```
kubectl get daemonsets
```
---
Descripción
```
kubectl describe ds fluentd-agent
```
---
Obtención del estado actual
```
kubectl rollout status ds fluentd-agent
```
---
Revisión de historico
```
kubectl rollout history ds fluentd-agent --revision=1
```
---
Actualización de versión en imagen
```
kubectl set image ds fluentd-agent fluentd=quay.io/fluentd_elasticsearch/fluentd:v4.6.2 --record
```
---
Rollback
```
kubectl rollout undo ds fluentd-agent --to-revision=1
```
---
Eliminación
```
kubectl delete ds fluentd-agent
```
---
