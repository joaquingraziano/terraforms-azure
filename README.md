# terra-azure

# Credentials
Usaremos las siguientes varibles subscription_id, client_id, client_secret, y tenant_id en el Portal de Azure. 
Estos son los pasos para configuracion e integracion con terraform.
```
Ingresamos al portal Azure https://portal.azure.com/.

# Variables:
## client_id
Ingresamos a Azure Active Directory >>
    Administrar / Registro de aplicaciones
    Creamos un nuevo registro, Le asignamos un nombre y el modo de acceso.
    Copiamos el ID de cliente que sera la variable client_id

## client_secret
Luego de crear el registro ingresamos y vamos Certificados y secretos
    Creamos un nuevo secreto de cliente y copiamos el "Valor" que sera nuestra variable client_secret

## tenant_id
Volvemos al Azure active directory / Informacion general y copiamos el "ID de inquilino" que sera nuestra variable tenant_id

## subscription_id
Ingresamos a nuestra suscripcion i copiamos el "ID de la suscripcion" que sera la variable subscription_id

## admin_ssh_key
generar una clave ssh y copiar el valor en variable admin_ssh_key


# Despliegue
```
El despliegue se realizo desde Terraform Cloud y se cargaron las variables para la conexion del provider.
Terraform Cloud
![Alt text](https://github.com/joaquingraziano/terraforms-azure/blob/main/img/Terraform-Planapply.jpg)
![Alt text](https://github.com/joaquingraziano/terraforms-azure/blob/main/img/RecursosCreadosazure.jpg)



# Errores encontrados

Problemas para loguearme a Azure cli
    Al dar error az login, borro el config de cd ~/.azure/ y reinicio la terminal

Me falto agregar el rol de la app a la suscripcion
    Ingresamos a la suscripcion / Control de acceso IAM 
        + agregamos asignacion de rol
        Roles de administrador con privilegios colaborador al miembro terraforms_azure
