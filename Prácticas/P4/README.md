# Práctica 4. Asegurar la granja web

## Objetivos de la práctica

El objetivo de esta práctica es llevar a cabo la configuración de seguridad de la granja web. Para ello, llevaremos a cabo las siguientes tareas:

- Instalar un certificado SSl para configurar el acceso HTTPS a los servidores.
- Configurar las reglas del cortafuegos para proteger la granja web.

## Cuestiones a resolver

El objetivo de esta práctica es configurar todos los aspectos relativos a la seguridad de la granja web ya creada.

Hay que llevar a cabo las siguientes tareas obligatorias:

1. Crear e instalar en la máquina 1 un certificado SSL autofirmado para configurar el acceso HTTPS a los servidores. Una vez configurada la máquina 1, se debe copiar al resto de máquinas servidoras y al balanceador de carga. Se debe configurar nginx adecuadamente para aceptar y balancear correctamente tanto el tráfico HTTP como el HTTPS.

En primer lugar debemos de tener instalado Apache en nuestra máquina:

```bash
  apt install apache2
```

Una vez instalado habilitamos ssl y restauramos el servicio:

```bash
  a2enmod ssl
  service apache2 restart
```

Creamos la carpeta `/etc/apache2/ssl`
Y generamos el certificado mediante este comando:

```bash
  openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt
```

Nos pedirá que ingresemos una serie de datos, tras esto, modificamos la siguientes líneas debajo de SSLEngine on del archivo `/etc/apache2/sites-available/default-ssl`:

```script
  SSLCertificateFile  /etc/apache2/ssl/apache.crt
  SSLCertificateKeyFile /etc/apache2/ssl/apache.key
```

Activamos el sitio `default-ssl` y reiniciamos apache:

```bash
  a2ensite default-ssl
  service apache2 reload
```

Ahora podemos comprobar con:

```bash
  curl -k https://ipmaquina/index.html
```

Realizando peticiones HTTPS. Todo estos pasos la hemos elaborado en las tres máquinas.

![Capturas balanceador]()

2. Configurar las reglas del cortafuegos con IPTABLES para asegurar el acceso a uno de los servidores web, permitiendo el acceso por los puertos de HTTP y HTTPS a dicho servidor. Esta configuración se hará en una de las máquinas servidoras finales (p.ej. en la máquina 1), y se debe poner en un script con las reglas del cortafuegos que se ejecute en el arranque del sistema (según la versión de Linux, se llevará a cabo de una forma u otra).

Adicionalmente, y como primera tarea opcional para conseguir una mayor nota en esta práctica, se propone realizar la instalación de un certificado del proyecto Certbot en lugar de uno autofirmado. Es importante tener en cuenta que para obtener este tipo de certificado, es necesario disponer de un dominio real con IP pública (no se puede hacer en máquinas virtuales).

Como segunda tarea opcional para conseguir una  mayor nota en esta práctica, se propone realizar la configuración del cortafuegos en una cuarta máquina (M4) que se situará delante del balanceador. Esa M4 sólo tendrá configuradas las iptables, para hacer el filtrado y posterior reencaminamiento del tráfico hacia el balanceador. En esta configuración más compleja sólo a esa M4-cortafuegos se le hará la configuración de iptables (el resto de máquinas de la granja tendrá la configuración por defecto, aceptando todo el tráfico como política por defecto.

- - -

## Grupo

  | [![Carlos Ariza García](https://github.com/AGCarlos.png?size=100)](https://github.com/AGCarlos) | [![Fernando Talavera Mendoza](https://github.com/Thejokeri.png?size=100)](https://github.com/Thejokeri) |
| :---: | :---: |
| [Carlos Ariza García](https://github.com/AGCarlos) | [Fernando Talavera Mendoza](https://github.com/Thejokeri) |