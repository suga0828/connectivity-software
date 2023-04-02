# Establecer una conexion SFTP a un servidor

SFTP es un protocolo de transferencia de archivos seguro que proporciona una capa adicional de seguridad sobre el protocolo FTP. SFTP es un protocolo seguro que proporciona autenticación y cifrado de datos.

### Instalacion

Para establecer la conexion con un servidor SFTP en CentOS 7.1, necesita instalar el paquete openssh-server. Para instalar el paquete, ejecute el siguiente comando:

```bash
yum -y install openssh-server openssh-clients openssl
```

### Verificacion del servicio SSH

Una vez instalado el paquete, el servicio SSH se encuentra deshabilitado. Para habilitarlo e iniciarlo, ejecute el siguiente comando:

```bash
systemctl enable sshd.service
```

```bash
systemctl start sshd.service
```

Para comprobar que el servicio este funcionando correctamente, puede usar el siguiente comando:

```bash
netstat -tulpn | grep sshd
```

![checking sshd service](../../images/checking-ssh.png)

Por defecto el servicio SSH esta configurado para escuchar en el `port 22`.

---

### Instalacion de FileZilla

[FileZilla](https://filezilla-project.org/download.php?type=client) es un cliente FTP y SFTP multiplataforma. Es un software de código abierto y gratuito.

### Conexion a un servidor usando SFTP en FileZilla

Para establecer una conexion SFTP a un servidor, debe configurar los siguientes parametros:

- **Host**: Nombre de dominio o direccion IP del servidor.
- **Port**: Puerto del servidor. Por defecto es el puerto 22.
- **Username**: Nombre de usuario con el que se va a conectar al servidor.
- **Password**: Contraseña del usuario.

![connecting to a server using sftp](../../images/filezilla-connection.png)
