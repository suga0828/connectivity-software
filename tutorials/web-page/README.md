## Despliegue de una pagina web en HTML

Las piezas de software involucradas en la simple consulta de una pagina web pueden ser varias y complejas. En esta guia se describe el proceso de configuracion, en servidores locales o remotos, de los servicios esenciales para la visualizacion de una pagina web.

#### Paso a paso

1. [Configuracion del DNS](../../services/dns-configuration/README.md), esencial para permitir que los usuarios accedan a la pagina web utilizando un nombre de dominio.
2. [Configuracion de un servidor web Apache](../../services/apache-server/README.md), software de servidor web mas comunmente utilizado.
3. [Creacion de una pagina web en HTML](../../services/html-web-page/README.md), para ser mostrada por el servidor web.
4. [Transferencia de archivos mediante SFTP](../../services/sftp/README.md), para subir la pagina web al servidor que contiene el servidor web.

Una vez completados los pasos anteriores, se puede acceder a la pagina web desde cualquier navegador web utilizando el nombre de dominio asignado al servidor web.

---

###### Solucion de problemas

Si la pagina web no se muestra correctamente y obtiene un error similar a `Check if there is a typo in name.domain. DNS_PROBE_FINISHED_NXDOMAIN`, debe asegurarse que está utilizando el DNS configurado.
