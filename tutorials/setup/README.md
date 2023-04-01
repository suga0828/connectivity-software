# Configuracion inicial de CentOS 7.1

Una vez que tengas instalado CentOS 7.1 en tu maquina virtual o en tu maquina fisica, y tengas conexion a internet puedes instalar los siguientes paquetes para que sigas los tutoriales de esta pagina:

Instalar VIM para editar archivos de texto:

```bash
  $ yum -y install vim-enhanced
```

Instalar el servicio DNS:

```bash
  $ yum -y install bind bind-chroot bind-utils bind-libs caching-nameserver
```

Instalar el servicio Apache:

```bash
  $ yum -y install httpd php
```

Instalar el servicio OpenSSH:

```bash
  $ yum -y install openssh-server openssh-clients openssl
```

Instalar el servicio Telnet:

```bash
  $ yum -y install telnet
```

Instalar `netstat`:

```bash
  $ yum -y install net-tools
```
