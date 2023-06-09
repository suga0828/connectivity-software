## Conexion a Internet de una maquina virtual en CentOS 7

Enciende tu marquina virtual e inicia sesión como root.

![login as root](../../images/login.png)

Desde aca, vamos al siguiente directorio:

```bash
  cd /etc/sysconfig/network-scripts
```

En este punto debemos ajustar la configuracion de la interfaz de la tarjeta de red que usaremos para conectarnos. **En mi caso es la `enp0s3`**.

Primero vamos a hacer un backup de nuevo archivo `ifcfg-enp0s3`, ejecutando el siguiente comando:

```bash
  cp ifcfg-enp0s3 ifcfg-enp0s3._backup
```

Para verificar que el backup fue creado correctamente ejecutamos el siguiente comando:

```bash
  ls -lah | grep ifcfg-enp0s3
```

![listing file to check if backup was successful](../../images/checking-interface-backup.png)

Ahora que tenemos el backup, vamos a editar el archivo `ifcfg-enp0s3` ejecutando:

```bash
  vi ifcfg-enp0s3
```

Actualiza las siguientes lineas:

```bash
  TYPE=Ethernet
  PROXY_METHOD=none
  BROWSER_ONLY=no
  BOOTPROTO=dhcp
  DEFROUTE=yes
  IPV4_FAILURE_FATAL=no
  IPV6INIT=yes
  IPV6_AUTOCONF=yes
  IPV6_DEFROUTE=yes
  IPV6_FAILURE_FATAL=no
  IPV6_ADDR_GEN_MODE=stable-privacy
  NAME=enp0s3
  UUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
  DEVICE=enp0s3
  ONBOOT=yes
```

Ahora, vamos a configurar la puerta de enlace en el archivo `/etc/sysconfig/network`. Para hacerlo ejecutamos:

```bash
  cd /etc/sysconfig
```

Nos aseguramos de hacer un backup de nuestro archivo `network`, ejecutando:

```bash
  cp network network_backup
```

Para verificar que el backup fue creado correctamente ejecutamos el siguiente comando:

```bash
  ls -lah | grep network
```

![listing file to check if backup was successful](../../images/checking-network-backup.png)

Ahora agreamos algunas lineas al archivo `network`:

```bash
  vi network
```

Debe ser un archivo vacio, agregamos las siguientes lineas:

```bash
  NETWORKING=yes
  HOSTNAME=centos7
  GATEWAY=192.168.10.1
```

Deberia quedar coi algo como esto:

![setting up gateway](../../images/setting-gateway.png)

El valor de `GATEWAY` es la puerta de enlace de tu maquina host. En este caso, es `192.168.10.1`.

Ahora vamos a configurar el name servers en el archivo `/etc/resolv.conf`. Para ir a la carpeta ejecutamos:

```bash
  cd /etc
```

Como siempre, hacemos un backup del archivo `resolv.conf` ejecutando:

```bash
  cp resolv.conf resolv.conf_backup
```

Para verificar que el backup fue creado correctamente ejecutamos el siguiente comando:

```bash
  ls -lah | grep resolv.conf
```

![listing file to check if backup was successful](../../images/checking-resolv-backup.png)

Ahora agregamos algunas lineas al archivo `resolv.conf`:

```bash
  vi resolv.conf
```

Inicialmente debe ser un archivo vacio, agregamos las siguientes lineas:

```bash
  nameserver 8.8.8.8
  nameserver 8.8.4.4
```

Antes de continuar tenemos que asegurarnos que nuestra maquina virtual tiene el adaptador de red configurado correctamente. En este caso estamos usando el adaptador NAT Network Adapter. **Si tienes que configurarlo y tu maquina virtual esta encendida, tienes que reiniciarla**.

![Network Adapter](../../images/network-adapter.png)

Ya casi estamos. Nos aseguramos de reiniciar el servicio de red ejecutando:

```bash
  systemctl restart network
```

Ahora, vamos a probar nuestra conexion a internet ejecutando:

```bash
  ping google.com
```

![ping google.com](../../images/checking-connection.png)

---

### Notas

Si quieres saber cual es la ip de tu maquina virtual, ejecuta:

```bash
  ip addr
```

![ip addr](../../images/ip-checking.png)
