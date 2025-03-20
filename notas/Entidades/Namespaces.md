[[Entidades]]

Si varios usuarios y equipos utilizan el mismo cluster, este se puede dividir en sub-clusters virtuales usando namespaces. Los nombres de los recursos creados dentro de un namespace son únicos, pero no entre los namespaces.

Generalmente Kubernetes te crear cuatro namespaces:
	** Kube-system. Este namespace contiene los objetos creados por el sistema, mayormente el control plane agents.
	** Defautl. Contiene los objetos y recursos creados por administradores y desarrolladores, los objetos son asignados automáticamente, a menos que se le especifíque el nombre de otro namespace.
	** kube-public. Tenia uso especial ya que expone información no sensible sobre el cluster, esta puede ser leída por todos.
	** kube-node-lease. Que contiene objetos usados para el monitoreo de la salud de los nodos.

Una buena practica es crear namespaces adicionales para un fin en especifico y aislar a los usuarios.
