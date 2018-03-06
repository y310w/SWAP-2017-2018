# Ejercicios del Tema 2

### 2.1 Calcular la disponibilidad del sistema si tenemos dos réplicas de cada elemento (en total 3 elementos en cada subsistema).


- Disponibilidades iniciales

| Component   | Availability |  
| ----------- | ------------ |
| Web         | 85 %         |
| Application | 90 %         |
| Database    | 99.9 %       |
| DNS         | 98 %         |
| Firewall    | 85 %         |
| Switch      | 99 %         |
| Data Center | 99.99 %      |
| ISP         | 95 %         |

- Con 2 elementos en cada subsistema

| Component   | Availability |  
| ----------- | ------------ |
| Web         | 97.75 %      |
| Application | 99 %         |
| Database    | 99.9999 %    |
| DNS         | 99.96 %      |
| Firewall    | 97.75 %      |
| Switch      | 99.99 %      |
| Data Center | 99.99 %      |
| ISP         | 99.75 %      |



Para calcular la nueva tabla que nos piden utilizaremos la siguiente ecuación:

    As = ACn-1 + ((1 - ACn-1) * ACn)

Dónde: 
- As: el nuevo porcentaje al añadir un nuevo componente 
- ACn-1: la disponibilidad del anterior
- ACn: la disponibilidad inicial


- Con 3 elementos en cada subsistema

| Component   | Availability |  
| ----------- | ------------ |
| Web         | 99.6625 %    |
| Application | 99.9 %       |
| Database    | 99.9999999 % |
| DNS         | 99.9992 %    |
| Firewall    | 99.6625 %    |
| Switch      | 99.9999 %    |
| Data Center | 99.99 %      |
| ISP         | 99.9875 %    |

La disponibilidad es: 99.6625 % * 99.9 % * 99.9999999 % * 99.9992 % * 99.6625 % * 99.9999 % * 99.99 % * 99.9875 % =  99.2035 %  

- - -

### 2.2 Buscar frameworks y librerías para diferentes lenguajes que permitan hacer aplicaciones altamente disponibles con relativa facilidad. 

### Como ejemplo, examina PM2  https://github.com/Unitech/pm2 que sirve para administrar clústeres de NodeJS.


- [Apache Hadoop](http://hadoop.apache.org): software que permite el procesamiento distribuido de grandes conjuntos de datos en grupos de computadoras que usan modelos de programación simples. 

- [Microsoft Operations Framework](https://technet.microsoft.com/en-us/library/dd320379.aspx): para productos de alta disponibilidad con tecnología Microsoft.

- Python: [Django](https://www.djangoproject.com), [TurboGears](http://quintagroup.com/cms/python/turbogears). [Más información](https://wiki.python.org/moin/WebFrameworks)

- JavaScript: [AJAX](https://es.wikipedia.org/wiki/Ajax_framework)

- PHP: [CakePHP](https://cakephp.org), [Zend](http://www.zend.com), [CodeIgniter](https://codeigniter.com)

- - -

### 2.3 Cómo analizar el nivel de carga de cada uno de los subsistemas en el servidor? Buscar herramientas y aprender a usarlas.

Todo estos son profilers para monitorizar nuestro servidor (Hardware, software, red, tasa de peticiones...):
- Nagios.
- Munin.
- Zabbix.

Herramientas internas de Linux:
- Top: muestra con una interfaz toda la ejecución de los procesos y se puede manejar de forma interactiva.    
- HTop: es igual que top pero muestra una barra de porcentaje del uso de cpu (de cada núcleo), memoria y swapping.
- ps: muestra de forma reducida y escasa, la información de procesos.
- uptime: muestra cuánto tiempo lleva la máquina en ejecución, además podemos ver si hay variaciones en la carga.

- - - 

### 2.4 Buscar ejemplos de balanceadores software y hardware (productos comerciales).

Software: HaProxy, Nginx, Kemp, Linux Virtual Server, Pound, Pen, Zen Load Balancer.

Hardware: CISCO, Load Balancer ADC, F5 BIG-IP LTM, AppDirector OnDemand, Coyote Point etc.

### Buscar productos comerciales para servidores de aplicaciones.

Ejemplos: GlassFish, Java EE, Sun-Netscape IPlanet, Orace IAS,
Base4 Server, HP Bluestone.

Otros servidores de aplicación:
- Internet Information Server, de Microsoft, para .NET.
- Base4 Server.
- Zope.


### Buscar productos comerciales para servidores de almacenamiento.

Ejemplos: Amazon EC2, Dell Compellent FS8600, IBM EXP2500 Storage Enclosure, Windows Azure, Lenovo ThinkServer, FlyTech, etc. 
