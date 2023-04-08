# Configuracion de un servidor de correo electronico

El correo electrónico es una de las aplicaciones más difíciles de configurar, ya que se tienen que activar varios servicios. Por ejemplo, se puede configurar SMTP3en el servidor de correo y hacerlo trabajar como MTA4 o usar SMTP para que el servidor reciba correo desde un MUA5.
También se puede configurar el servidor como MDA6 para la entrega de correos a un usuario usando el protocolo POP3 o IMAP.

Para la instalación de un servidor de correo se pueden utilizar diferentes programas, los cuales son funcionales sobre entornos GNU/Linux. De esta manera, se tienen los programas Qmail, Exim, MsExchange, Sendmail o Postfix; todos cuentan con soporte para IPv6.

###### [Configuracion del servicio Postfix](../../services/postfix-configuration/README.md)

###### [Configuracion del servicio Dovecot](../../services/dovecot-configuration/README.md)

###### [Creacion de usuarios para el sistema de correo](../create-user/README.md)

###### [Configuracion de un cliente de correo](../email-client/README.md)

Una vez completados los pasos anteriores, se puede enviar y recibir correos electrónicos desde el servidor hacia direcciones dentro del dominio especificado en el archivo de configuración de Postfix.

---
