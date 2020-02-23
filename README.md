# Keycloak

## Acerca de Keycloak

Keycloak es una solución de inicio de sesión único para aplicaciones web y servicios REST.

El objetivo de Keycloak es simplificar a los desarrolladores la implementación de la seguridad de las aplicaciones al proveer de forma inmediata las características que normalmente se tienen que escribir por sí mismas. Con Keycloak se pueden asegurar aplicaciones escribiendo muy poco código.

Keycloak proporciona interfaces de usuario personalizables para inicio de sesión y registro,y también se puede delegar la autenticación a proveedores de identidad de terceros como Facebook y Twitter.

## Principales características

* Servidor de autenticación con soporte para Single Sign One / SSO.
* Keycloak está basado en protocolos estándar y provee soporte para OpenID Connect, OAuth 2.0, y SAML.

## Instalación e inicialización

Para este tutorial se usará la distribución en formato zip y la versión a utilizar es la 8.0.2. Este es el link de descarga: https://www.keycloak.org/archive/downloads-8.0.2.html

> Recientemente se liberó la versión 9. Es problable que los ejemplos presentados funcionen correctamente en esta versión, pero aún no han sido probados.
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

Después de que inicia el servidor Keycloak hay que abrir la url http://localhost:8080/auth en el navegador e ingresar un nombre de usuario y contraseña para crear el usuario admin incial.

Con estas credenciales se puede ingresar a la consola de administración de Keycloak.

## Creación de un Realm y un usuario

