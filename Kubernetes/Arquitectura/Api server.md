[[Arquitectura]]

Todas las tareas son coordinadas por el **api server**, este es ejecutado en el control plane node. Este api server recibe todas las peticiones entrantes RESTful de usuarios, administradores, desarrolladores, etc.
Durante el proceso de una petición lee el estado del cluster desde la base de datos y despues de su llamado al nodo, guarda el resultado de la operación.
Este componente es el unico que se puede comunicar con la BD.
El api server es altamente configurable y puede ser escalado horizontalmente.
