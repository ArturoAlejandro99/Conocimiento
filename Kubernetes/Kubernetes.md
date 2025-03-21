#kubernetes 
## Qué es un monolito?
Es un sistema altamente acoplado todas sus reglas de negocio y funcionalidades a un sistema, por lo general con código legado y en ocasiones incluso con alta acoplación a la base de datos.

## Qué es un microservicio?
Es un sistema que contiene una funcionalidad en un sistema. Al contrario de un monolito, se crean diferentes microservicios para contener una lógica de negocio especifica.

Ventajas
	No existe acomplamiento en el sistema
	 Se puede escalar vertical y horizontalmente acorde a las necesidades en tiempo real
	 Previene posibles caídas enteras de todo el sistema
	 Mejor colaboración al momento de desarrollar funcionalidades del sistema

### Como migrar un sistema monolitico a microservicios
Existen dos formas de migrar un sistema:
**Big bang**
Consiste en detener el desarrollo de nuevas funcionalidades del sistema monolitico y empezar desde cero la migración de funcionalidades a una aquitectura de microservicios.
Es recomendable utilizar este forma para sistemas que cuenta con un código legado o sistema que se encuentran altamente acoplados con bases de datos.

**Refactorización incremental**
Consiste en ir migrando funcionalidades de manera incremental.
En este enfoque se pueden seguir realizando nuevas features a los sistemas (migrando la funcionalidad a un microservicio e  implementar la feature), se sigue manteniendo el monolito y se realizan modificaciones para ir implementado las funcionalidades de los microservicios.