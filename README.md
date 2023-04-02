# Software de Conectividad

En este repositorio encontrará guias para la configuracion de algunos servicios relacionados al software de conectividad en las redes.

##### Requisitos

- [Sistema operativo CentOS 7.1 (version Minimal-2009)](https://www.centos.org/download/). Puede instalarlo en una maquina virtual con [VirtualBox](https://www.virtualbox.org/wiki/Downloads) o en una maquina fisica.
- Ejecutar la [configuracion inicial](tutorials/setup/README.md) para instalar las herramientas necesarias para seguir los tutoriales.

## Guias

- [Despliegue de una pagina web en HTML](tutorials/web-page/README.md)
<!-- - [Configuracion de servidor de correos](tutorials/email-server/README.md) -->

---

## Anexos

- [Instalacion de CentOS 7.1 en VirtualBox](https://linuxdukes.com/how-to-install-centos-7-in-virtualbox/)
- [Conexion a internet de una maquina virtual CentOS 7.1](tutorials/internet-connection/README.md)

---

## Desarrollo local

Para trabajar con el proyecto localmente, se debe instalar <a href="https://www.mkdocs.org/getting-started/" target="_blank">MkDocs</a>, el tema <a href="https://squidfunk.github.io/mkdocs-material/" target="_blank">Material for MkDocs</a> y el plugin <a href="https://github.com/oprypin/mkdocs-same-dir" target="_blank">mkdocs-same-dir</a>.

##### Instalacion

```bash
  pip install mkdocs mkdocs-material mkdocs-same-dir
```

##### Ejecucion

```bash
  mkdocs serve
```

##### Despliegue

```bash
  mkdocs gh-deploy
```
