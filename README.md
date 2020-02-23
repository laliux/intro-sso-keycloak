# Keycloak

## Acerca de Keycloak

Keycloak es una solución de inicio de sesión único para aplicaciones web y servicios REST.

El objetivo de Keycloak es simplificar a los desarrolladores la implementación de la seguridad de las aplicaciones al proveer de forma inmediata las características que normalmente se tienen que escribir por sí mismas. Con Keycloak se pueden asegurar aplicaciones escribiendo muy poco código.

## Principales características

* Servidor de autenticación con soporte para Single Sign One / SSO.
* Keycloak proporciona interfaces de usuario personalizables para inicio de sesión y registro,y también se puede delegar la autenticación a proveedores de identidad de terceros como Facebook y Twitter.
* Keycloak está basado en protocolos estándar y provee soporte para OpenID Connect, OAuth 2.0, y SAML.

## Requerimientos de sistema

* Cualquier sistema operativo con soporte para Java 8
* Mínimo 512M de RAM
* Por lo menos 1G de espacio en disco

## Instalación e inicialización

Para este tutorial se usará la distribución en formato zip y la versión a utilizar es la 8.0.2. Este es el link de descarga: https://www.keycloak.org/archive/downloads-8.0.2.html

> Recientemente se liberó la versión 9. Es problable que los ejemplos presentados funcionen correctamente en esta versión, pero aún no han sido probados.
> 
> Por defecto Keycloak usa una base de datos embebida H2 para la persistencia de datos. Esta base de datos es recomendada sólo para pruebas y desarrollo, para ambientes de producción se debe usar una base de datos más robusta como MySQL, PostgreSQL u Oracle, cualquiera con un driver JDBC.

Descomprimir

```
$ unzip keycloak-8.0.2.zip
```

Iniciar el servidor

```
$ cd keycloak-8.0.2
$ ./bin/standalone.sh
```

## Creación de la cuenta Admin

Después de que inicia el servidor abrimos la url http://localhost:8080/auth en el navegador e ingresamos un nombre de usuario y contraseña para crear el usuario admin incial.

Con estas credenciales ingresaremos a la consola de administración de Keycloak.

## Creación de un Realm y un usuario

Un realm administra un conjunto de usuarios, credenciales, roles y grupos. Un usuario pertenece a un realm y un realm sólo puede autenticar y administrar a los usuarios que éste mismo controla.

Para crear un realm iniciamos sesión con el usuario admin creado previamente,  http://localhost:8080/auth/admin/ .

Desde el menú desplegable en el lado superior izquierdo seleccionamos "Add Realm". El realm de ejemplo se llamará **jvmmx**.

Para crear un usuario usamos el menú "Users" del lado inzquierdo de la consola de administración, después damos click al botón "Add User". El único valor requerido es el username. Ponemos **demo**, cambiamos el campo "Email Verified" a "ON" y guardamos.

Una vez que el usuario es creado seleccionamos la pestaña "Credentials" para asignar una contraseña temporal. Ponemos **hola123** y guardamos.

Para confirmar los datos de acceso nos dirijimos a http://localhost:8080/auth/realms/jvmmx/account e ingresamos con demo/hola123.

Se nos pedirá que cambiemos la contraseña pues la que asignamos previamente era temporal. Entonces estaremos en la página de la cuenta del usuario desde donde se pueden actualizar datos personales. En esta parte podemos simplemente cerrar la sesión.
