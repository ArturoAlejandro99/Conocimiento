[[Arquitectura]]
Este nodo provee una ambiente para la ejecución de aplicaciones.
Estas aplicaciones son microservicios ejecutados como contenedores.
En Kubernetes los contenedores son encapsulado en pods controlados por el control plane (el maestro) 
Cada pod es programado en un worker node, donde encuentran los requisitos para ser ejecutados.

Un pod es la unidad más pequeña en kubernetes. Es una colección de uno o muchos contenedores.

En un ambiente multi worker, el trafico de cliente y pods es manejada directamente por los workers y no es enrutada por el control plane node.

Un worker contiene los siguientes componentes:
	Container runtime
	Node Agent ([[Kubelet]])
	Proxy ([[kube-proxy]])
	Adiciones para logging, observabilidad, etc.