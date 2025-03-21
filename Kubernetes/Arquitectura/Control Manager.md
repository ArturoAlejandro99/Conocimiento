[[Arquitectura]]

Es el componente encargado de manejar el estado del cluster.
Los controladores se ejecutan todo el tiempo vigilando y comparando el estado del cluster con la información de la bd via API server. En caso de que no coincida corregir la acción.

El kube-controller-manager ejecuta controladores y operaciones cuando los nodos se vuelven no disponibles, para asegurar la cantidad de pods esperada, crear endpoints, cuentas, y API access tokens.

El cloud-controller-manager al igual que el anterior ejecuta controladores y operadores encargados de interactuar con la infraestructura de nube del proveedor. 
Este maneja las misma operaciones que el anterior, adicionando el manejo del balanceador y ruteado.
