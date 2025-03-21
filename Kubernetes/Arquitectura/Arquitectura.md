[[Kubernetes]]

![[Arquitectura K8s.png]]

El control plane nodo provee un ambiente para el control de workers o nodos y es el encargado de manejar el estado del cluster de kubernetes y todas sus operaciones por detras.

Es importante mantener vivo el control plane a toda costa, ya que puede provocar caiudas de los servicios en caso de no mantenerse levantado.

Para asegurar la tolerancia a fallos es posible generar variables replicas de este **maestro**, donde solo un maestro tiene el control de los workers y las replicas se mantiene constantemente sincronizadas añadiendo resilencia al cluster de control plane.

El manejador de estado y toda su configuración es alojada en una base de datos de tipo llave valor (etdc)

El control pane ejecuta los siguientes componentes y agentes necesarios:
	[[Api server]]
	[[Scheduler]]
	[[Control Manager]]
	Key-Value data store ([[etcd]])

Para cada [[Worker node]] o nodo se ejecutan los siguientes componentes:
	Container runtime (contenedor)
	Node Agent (kubelet)
	Proxy (kube-proxy)
	Componentes opcionales para observabilidad como dashboards, monitoreo a nivel cluster y logging