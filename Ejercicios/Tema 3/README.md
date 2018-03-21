# Ejercicios del Tema 3

### 3.1 Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el enrutamiento del tráfico de un servidor para pasar el tráfico desde una subred a otra.

En Linux el comando para pasar el enrutamiendo del tráfico de una subred a otra es `route`.

Con `route` podemos añadir (`add`) y eliminar (`del`) rutas.

Además podemos configurar el tráfico de red siguiendo este [tutorial](http://www.ite.educacion.es/formacion/materiales/85/cd/linux/m6/enrutamiento_en_linux.html) de enrutamiento en Linux, utilizando `iptables`

Para Windows, en Windows Server podemos añadir un Servicio de enrutamiento y acceso remoto.

Además hay una serie de software de terceros que nos proporcionan una interfaz para el enrutamiento del tráfico de un servidor:

- [OpenBGD](http://es.wikipedia.org/wiki/OpenBGPD).
- [Quagga](http://es.wikipedia.org/wiki/Quagga_(enrutador)).
- [XORP](http://xorp.org/).
- BIRD.
- GNU Zebra.
- [Manage Engine](https://www.manageengine.com/free-ping-tool/free-ping-tool-index.html).
- [Angry IP Scanner](http://angryip.org/about/).
- Bitcricket IP Subnet Calculator (Windows).
- [Pinkie](http://www.ipuptime.net/pinkie/)


- - -

### 3.2 Buscar con qué órdenes de terminal o herramientas gráficas podemos configurar bajo Windows y bajo Linux el filtrado y bloqueo de paquetes.

Linux:
- iptables, ip o tc.
- ufw.

Windows:
- [Windows Server 2003](https://support.microsoft.com/es-es/help/816792/how-to-configure-tcp-ip-filtering-in-windows-server-2003).
- route

Herramientas gráficas

- Shorewall.
- WireShark.
- PRTG.
- CocoaPacket Analyzer.
- Acrylic Wifi.