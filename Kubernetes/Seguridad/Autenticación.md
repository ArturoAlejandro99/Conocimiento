Kuebernetes puede utilizar nombre de usuarios para la autenticación en la fase del api access control.

Soporta dos tipos de usuarios:

Normal Users: Son manejados por terceros como certificados usuario/cliente, usuario/password. cuentas google, etc.

Services Accounts: Permite comunicarse con el api server y realizar varias operaciones. El service account están relacionadas a particulares namespace y volúmenes para comunicarse con el api server como secrets.

