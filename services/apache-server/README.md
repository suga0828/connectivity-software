# Configuracion de un servidor Apache

Apache es un software de servidor web de código abierto que se utiliza para alojar sitios web en Internet. Es uno de los servidores web más populares y se utiliza en una gran cantidad de sitios web en todo el mundo.

Proporciona una variedad de características y funcionalidades para alojar sitios web, incluyendo soporte para lenguajes de programación como PHP, Python y Perl, y una amplia variedad de módulos y complementos.

### Instalacion de paquetes

Para instalar el servidor DNS (BIND) en CentOS 7.1, ejecute el siguiente comando:

```bash
yum -y install httpd php
```

---

### Configuracion del servicio httpd

Primero vamos a configurar el archivo de configuracion principal del servidor httpd, el cual se encuentra en la ruta `/etc/httpd/conf/httpd.conf`.

```bash
vim /etc/httpd/conf/httpd.conf
```

En el archivo de configuracion, debemos agregar la siguiente configuracion:

```
ServerName apache.example.com
```

Donde apache.example.com va a ser el nombre de dominio donde va a estar alojado el sitio web.

Una vez instalado el paquete, el servicio httpd se encuentra deshabilitado. Para habilitarlo e iniciarlo, ejecute el siguiente comando:

```bash
systemctl enable httpd.service
```

```bash
systemctl start httpd.service
```

Tambien puede verificar el estado del servicio o detenerlo con los siguientes comandos:

```bash
systemctl status httpd.service
```

```bash
systemctl stop httpd.service
```

Para verificar que el servicio este funcionando correctamente puede usar el siguiente comando:

```bash
netstat -tulpn | grep httpd
```

---

### Carga del sitio web

Para cargar el sitio web en el servidor, debe copiar el contenido del sitio web en la ruta `/var/www/html`. Para ello, puede usar una [conexion SFTP](../sftp/README.md). Puedes usar un archivo como este [index.html](./index.html)

---

### Acceso al sitio web desde un navegador

Para acceder al sitio web desde un navegador, debe ingresar la direccion IP del servidor en la barra de direcciones del navegador. Adicionalmente, si tienes configurado un servicio DNS puedes usar el nombre de dominio configurado como `ServerName` en el servidor Apache.
