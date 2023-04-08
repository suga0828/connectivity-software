# Configuracion de un servicio Postfix

Postfix es un servidor de correo de código abierto, un programa informático para el enrutamiento y envío de correo electrónico. Postfix es el agente de transporte por defecto en diversas distribuciones de Linux y en las últimas versiones del Mac OS X.

### Instalacion de paquetes

Para instalar el servicio Postfix en CentOS 7.1, ejecute el siguiente comando:

```bash
yum -y install postfix
```

---

### Configuracion de archivos

- Archivo de configuracion [/etc/postfix/main.cf](#etcpostfixmaincf).
  - [_myhostname_](#myhostname)
  - [_mydomain_](#mydomain)
  - [_myorigin_](#myorigin)
  - [_inet_interfaces_](#inet_interfaces)
  - [_inet_protocols_](#inet_protocols)
  - [_mydestination_](#mydestination)
  - [_mynetworks_](#mynetworks)
  - [_smtp_bind_address6_](#smtp_bind_address6)
  - [_broken_sasl_auth_clients_](#broken_sasl_auth_clients)
  - [_append_dot_mydomain_](#append_dot_mydomain)

#### /etc/postfix/main.cf

Postfix tiene varios cientos de parámetros de configuración que se controlan a través del archivo `main.cf`. Afortunadamente, todos los parámetros tienen valores predeterminados razonables. En muchos casos, necesita configurar solo dos o tres parámetros antes de iniciar el sistema de correo.

#### _myhostname_

El nombre de host del servidor de correo electrónico. Este parámetro es obligatorio. El valor predeterminado es el nombre de host del sistema.

```bash
myhostname = correo.example.com
```

#### _mydomain_

El nombre de dominio del servidor de correo electrónico. Este parámetro es obligatorio. El valor predeterminado es el nombre de dominio del sistema.

```bash
mydomain = example.com
```

#### _myorigin_

```bash
myorigin = $mydomain
```

#### _inet_interfaces_

La dirección IP del servidor de correo electrónico. Este parámetro es obligatorio.

```bash
inet_interfaces = all
```

#### _inet_protocols_

El protocolo de red que se utilizará para enviar y recibir correo electrónico. Este parámetro es obligatorio. Algunos valores posibles son: `all`, `ipv4`, `ipv6` o combinaciones de estos dos últimos separados por comas.

```bash
inet_protocols = all
```

#### _mydestination_

El nombre de dominio del servidor de correo electrónico.

```bash
mydestination = example.com
```

#### _mynetworks_

El nombre de dominio del servidor de correo electrónico.

```bash
mynetworks = [::]
```

#### _smtp_bind_address6_

```bash
smtpd_bind_address6 = 2001:db8:1::101
```

#### _broken_sasl_auth_clients_

Habilite la interoperabilidad con clientes SMTP que no siguen las especificaciones de autenticación SASL anunciando la compatibilidad con AUTH de una manera no estándar.

```bash
broken_sasl_auth_clients = yes
```

#### _append_dot_mydomain_

```bash
append_dot_mydomain = no
```

---

### Verifcacion del servidor de correo electronico

Primero podemos habilitar, reiniciar y verificar el estado el servicio:

```bash
systemctl enable postfix
systemctl restart postfix
systemctl status postfix
```

Para verificar que el servidor de correo esta desplegado adecuadamente, ejecute el siguiente comando:

```bash
netstat -tulpn | grep 25
```

Para verificar el funcionamiento del servidor de correo, probamos la conexion al servidor ejecutando el siguiente comando:

```bash
telnet smtp.example.com 25
```
