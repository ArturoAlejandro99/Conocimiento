[[Entidades]]
Labels son pares de llave-valor relacionados a objetos de kubernetes como pods, replicasets, nodes, namespaces and persistent volumes.
Es una manera de organizar objetos en kubernetes.

![[Pasted image 20250320104835.png]]

En está imagen se muestra como ejemplo etiquetas app y env.

Existen dos tipos de selectores de labels:

**Equality-Bases Selectors**: permite el filtrado de objetos con base a su llave-valor. Se puede utilizar los operadores "=", == o "!="
**Set-Based Selector**: permite el filtrado con base a el seteo de valores.
Se pueden utilizar operadores como **in**, **notin**, **exist**, **does not exist**

![[Pasted image 20250320105451.png]]