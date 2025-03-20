[[Entidades]]

Los nodos son entidades virtuales asignadas por kubernetes. Su propósito es el manejo de los recursos y monitoreo lo que ayuda al manejo de la carga de trabajo de cluster.
Cada nodo es manejado con la ayuda de dos agentes, kubelet y kube-proxy, al igual mantiene un container runtime.

El container runtime es requerido para ejecutar toda la carga de trabajo contenerizada en el nodo, control plane y user workloads.

El kubelet y kube-proxy es el encargado de ejecutar todas las tareas locales, interactuar con el runtime para ejecutar los contenedores, monitoreas y validar las healt validations, reportar cualquier problema a el api server y manejar el trafico.


