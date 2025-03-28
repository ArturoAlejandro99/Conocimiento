Después de haber sido autenticado, es posible utilizar diferentes mecanismos de autorización. A continuación se enlistan.

**Node**: Autorización para realizar solo por nodo, por ejemplo services, edpoint, nodes, o escribir operaciones por nodo, pods, y eventos.

**Attribute-Based Access Control (ABAC)**: Con este tipo de autorización permites realizar consultas a la API combinando varios atributos, en el siguiente ejemplo el usuario Bob solo puede leer pods en el namescpace lfs158.

```
{
  "apiVersion": "abac.authorization.kubernetes.io/v1beta1",
  "kind": "Policy",
  "spec": {
    "user": "bob",
    "namespace": "lfs158",
    "resource": "pods",
    "readonly": true
  }
}
```

para habilitar el ABAC es necesario inicializar el API server con **--authorization-mode=ABAC --authorization-policy-file=PolicyFile.json**

**Webhook**: kubernetes puede autorizar por medio del servicio de un tercero el cual retornara una autorización.

**Role-Based Access Control (RBAC)**:
Es la autorización por medio de roles a usuarios específicos. Los roles puedes ser otorgados a usuarios, services account, etc. Cuando se crean roles, se restringen los recursos por medio de operaciones como create, get, update, patch, etc. En RBAC se pueden crear dos tipos de roles.

	Role: un rol puede dar acceso a un recurso sin especificar el namespace

	ClusterRole: es igual que un rol pero con alcanze limitado a un cluster

```
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  namespace: lfs158
  name: pod-reader
rules:
- apiGroups: [""] # "" indicates the core API group
  resources: ["pods"]
  verbs: ["get", "watch", "list"]
```
Ejemplo de un Rol

```
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: cluster-admin
rules:
- apiGroups:
  - '*' # All API groups
  resources:
  - '*' # All resources
  verbs:
  - '*' # All operations
- nonResourceURLs:
  - '*' # All non resource URLs, such as "/healthz"
  verbs:
  - '*' # All operations
```
Ejemplo de un ClusterRol

Una vez creado el rol, este puede ser relacionado a un usuario con RoleBinding object. Existen dos tipos de RoleBinding.

	RoleBindign: Permite bindear a usuarios con el mismo namespace que el Rol. Tambien se puede referir a un ClusterRole en RoleBinding el cual otorgaria permiso a un namespace.

	ClusterRoleBinding: Permite dar acceso a un recurso a nivel de cluster y a todos los namespaces.

Ejemplo de RoleBinding.
```
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: pod-read-access
  namespace: lfs158
subjects:
- kind: User
  name: bob
  apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role
  name: pod-reader
  apiGroup: rbac.authorization.k8s.io
```

Ejemplo de ClusterRoleBinding.
```
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: cluster-admin
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
- apiGroup: rbac.authorization.k8s.io
  kind: Group
  name: system:admins
```

Para habilitar RBAC es necesario iniciar el API server con **--authorization-mode=RBAC**
