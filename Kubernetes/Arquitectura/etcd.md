[[Arquitectura]]
Es una potente base de datos de llave-valor distribuida usada para mantener el estado del cluster de kubernetes.

La información nueva es añadida, la información almacenada nunca es remplazada. La información obsoleta es compactada o eliminada.

Es importante que en modo productivo replicar esta base de datos para mantener resilencia.

etdc también es utilizado para guardar la configuración de subnets, configmaps, secrets, etc.
