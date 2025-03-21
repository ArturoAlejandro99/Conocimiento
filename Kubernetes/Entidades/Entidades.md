[[Kubernetes]]

Kubernetes es el encargado de manejar el estado de diferentes entidades, esas entidades están descritas como:

	Aplicaciones que estan contenerizadas.
	Los nodos donde nuestras aplicaciones están desplegadas.
	Los recursos de una aplicación
	Politicas relacionadas a una aplicación, como politicas de reinicio y actualización, tolerancia a fallos, ingress/egress, access contro, etc.

Donde cada objecto se encuentra declarodo en la sección del spec. Kuebernetes es el sistema encargado de manejar el estado de estos diferentes objetos.

Algunos ejemplos de tipos de objetos son nodos, namespaces, pods, replicasets, deployments, daemonsets, etc.

El kubernetes api server es el encargado de la creación de estos objetos. Aún que comunmente se definen en un manifiesto YAML el kubectl es el encargado de convertir estos archivos a formato JSON para que puedan ser procesados por el API server.
