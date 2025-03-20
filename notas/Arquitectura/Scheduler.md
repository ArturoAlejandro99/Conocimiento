[[Arquitectura]]

El trabajo de este componente es asignar nuevos objetos de trabajo a un worker en especifico. Durante el proceso del scheduler, se toman desiciones basadas en el estado actual del cluster y los requerimientos de los nuevos objetos.
El scheduler obtiene información del estado por medio del API server. De este también obtiene los requerimientos de creación del nuevo objeto como tamaño de disco, procesamiento etc.
Cuando tiene toda la información el algoritmo interno se encarga de filtrar y seleccionar el posible worker node que satisface las necesidad del nuevo objeto.
La decisión es comunicada al Api Server el cual delega la responsabilidad de desplegar el objeto con otro agente del control plane.
