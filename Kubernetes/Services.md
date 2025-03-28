[[Kubernetes]]
Los services agrupan pods y define políticas para acceder a ellos. Estos grupos son generados por medio de Etiquetas y selectores.

![[Pasted image 20250324111647.png]]


El siguiente es el ejemplo de una definición de una servicio.


```
apiVersion: v1
kind: Service
metadata:
  name: frontend-svc
spec:
  selector:
    app: frontend
  ports:
  - protocol: TCP
    port: 80
    targetPort: 5000
```

