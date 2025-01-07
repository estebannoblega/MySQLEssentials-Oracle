# 1 - MySQL Enterprise Edition
### ¿qué es mysql?
* Es un sistema de gestión de basese de datos relacionales que organiza los datos en filas y columnas estructuradas para un eficiente manejo de los datos.
* Utiliza transacciones que permiten realizar insercion, lectura, borrado y edicion de datos. La transaccion se guarda solo si cada parte se completa correctamente.
* Utiliza como motor de almacenamiento el llamdo InnoDB, que permite manejar operaciones complejas y grandes volumenes de datos.
* Es capaz de realizar transacciones rápidamente y gestionar grandes volúmenes de transacciones a la vez. Utiliza OLTP: Low Latency, High throughput. Haciendolo ideal para entornos de alta velocidad.
* Almacena datos y los replica en uno o varios servidores, mejorando la disponibilidad de los datos y el equilibrio de carga.
* Es un sistema de gestión de bases de datos relacionales que soporta SQL, incluye almacenamiento de documentos permitiendo la creación de apliaciones SQL y NoSQL sin necesitar de una BD NOSQL independiente. También incluye funciones de seguridad avanzada para proteger la integridad y la privacidad de los datos.
* MySQL es de código abierto, lo que quiere decir que cualquiera puede descargarlo y usarlo de forma gratuita. Sin embargo hace uso de la licencia GPL (que habla sobre la comercializacion y distribución del software)
* Está disponible en dos ediciones:
    * MySQL Community Edition: Disponible de forma gratuita que incluye funciones principales y necesarias.
    * MySQL Commercial Edition: Para empresas, ofrece funciones avanzadas, herramientas de gestión y soporte técnico dedicado.
#### MYSQL COMMERCIAL PRODUCTS

### Soporte MySQL
Mysql Enterprise support porporciona acceso directo al equipo de soporte de mysql. Funciona a nivel mundial y está disponible en 29 idiomas. Ofrece actualizaciones. Está disponible 24x7. No incluye restricciones en la cantidad de consultas. Ofrece orientación y asesoramiento.

### Herramientas y Funciones Avanzadas
* Mysql Shell:
    Herramienta de cliente integrada que se utiliza para todas las oearaciones de mysql y las funciones administrativas.
    Ofrece soporte en varios lenguajes ej: js, python y SQL
* MySQL Server:
    Permite la gestion tanto SQL como NoSQL. Incluye un analizador que interpreta los comandos SQL, un optimizador ejecutar consultas de manera eficaz.
    Por defecto usa InnoDB como motor de almacenamiento.
* Mysql Enterprise Tools:
    Son herramientas exclusivas de este plan. Diseñadas para implementaciones a nivel empresarial. Tambien incluye plugins, como firewall, auditorias, encriptacion, etc.
* MySQL Enterprise Management Tools:
    Enterprise Bakcup,Workbench, Monitor (Performance y disponibilidad. Visualizar problemas en queries, permite realizar pre ),Auditorias, firewall
    encriptacion asimetrica (gestiona claves de acceso). Cifrado de datos transparentes. Masking (enmascaramniento - ofrece confidencialidad)
* Mysql HeatWave in te Cloud:
    Ofrece un servicio mysql gestionado totalmente, porporciona despliegue, copia de seguridad y restauración, alta disponibilidad, cambio de tamaño, etc.
    Es una infraestructura potente que nace de la union de oracle y mysql.
### Preguntas MODULO 1

1- which servico does mysql heatwaVE OFFER
"MySQL HeatWave offers a fully managed MySQL service. It provides deployment, backup and restore, high availability, resizing, and read replicas—all the features you need for efficient database management."
2- which statement is true about mysql Workbench enterpriese
"MySQL Workbench Enterprise simplifies database migrations with powerful tools that make it easy to move databases between platforms. It streamlines the process of moving databases between systems, thereby reducing time and errors."
3 -for which language does mysql shell offer support
"MySQL Shell offers multilanguage support for JavaScript, Python, and SQL. These naturally scriptable languages make coding flexible and efficient. They allow developers to use their preferred programming language for everything from automating database tasks to writing complex queries."
4 - whoy many major editions does mysql offer
"MySQL offers two major editions: For developers and small teams, the Community Edition is available for free and includes all the core features needed. For larger enterprises, the Commercial Edition provides advanced features, management tools, and dedicated technical support."
5 - what does the oracle commercial licensing option allow businesses to do?
"Oracle provides a commercial licensing option. This license allows businesses to use MySQL in their products without having to disclose their source code, as required by GPL v2."
6 - when is mysql enterprise support available?
"MySQL Support is available 24 hours a day, 7 days a week. This ensures that whenever there is an issue, Oracle support can provide the needed help without any delay."


# 3. MySQL Installation and Achitecture
## Instalación y Arquitectura
### Preparacion de instalacion
Mysql es soportado en muchas distros linux, macos y windows. Se puede ejecutar en un servidor dedicado, virtualizado o sala de servidores en centros de datos. Tambien desplegarse sobre contenedores.
Es multi-threading y es compatible con el aaceso a memoria no uniforme o NUMA (util en sistemas con muchas conexiones simultaneas)
El motor de almacenamiento InnoDB mejor el uso de la memoria disponible ya que almacena los datos activos en un pool de buffers, lo que aumenta el tiempo de acceso en comparación con la lectura directa del disco. 
La redundancia en fuentes de alimentación, almacenamiento, red es un punto importante. Sin redundancia un punto de falla hará que todo el servidor falle.
### Descarga de MySQL
Se descarga del enlace, la mas popular es la bvCommunity Edition (no tiene costo).
Es de codigo abierto.
La version Enterprise es soportada en oracle.
Si se quiere probar las opciones de pago se puede utilizar la version Enterprise pero en su versión de prueba. 
Se puede descargar el codigo fuente de la pagina de mysql o de github.
### Musql LTS and Innovbation Releases
LTS significa soporte a largo plazo, la version 8.4 es una version LTS.
LTS son estables, se pueden aplicar parches de seguridad si cambiar el comportamiento.
lTS se lanzan cada 2 años, esto permite tener un sistema estable.
Innovation Releases: estas versiones contienne las últimas características de vanguardia que se desarrollan incluso en medio de un lanzamiento de LTS.
Se puede pasar de una versión a otra sin problema en cualquier momento.
Nuevas caracteristicas cdada trimestre. -- esto tiene como desventaja que hay qye estar actualizando el servidor con mayor frecuencia que con las versiones LTS.
Ambas versiones estan listas para ejecutarse en producción.
El soporte brinda soluciones en formatosde parches.
Musql tiene documentación detallada.
### Mysql Installation
La documentación indica el paso a paso de la instalación.
En windwos tenemos:
    - Mysql Installer: es la mas sencilla. Instal y realiza la configuración iniical en función de las opciones que se elijen para la instalación. Incluye tambien conectores, shell, workbench y utilidades para resolución de problemas y la administración. Utiliza un asistente de instalación permite seleccionar la ubicación de instalación, componentes etc.
    - Binario Zip: No incluye herramientas de soporte y conectores, sino que solo contiene los binarios de la apliacaión que puede instalarse en donde se desee. La configuración inicial no se realiza seleccionando una opción mediante un asistente, se debe hacer editando un archivo de configuración.
En linux es muy variable debido a las distintas distribuciones (ya que cada una cuenta con un gestor de paquetes diferentes):
    - YUM para instalar los RPM. 
    - La decisión del instalador depende de los requerimientos del cliente, cuanto sabe sobre configuración y que tipo de servidor desea desplegar.
    - Algunas distribuciones no instalan mysql cuando utiliza un opackage manager. Suelen utilizar versiones bifurcadas de mysql (no es software de mysql).
    - Se debe conectar el gestor de paquetes a los repositorios oficiales de mysql.
    - Requiere que tenga dependencias instaladas (en gral el gestor de paquetes las instala antes de instalar mysql en sí). Son libaio (utilizado para opraciones de entrada/salida asíncronas). lib64 (utilizada para mostrar texto en la apliación de consola)
    - Los gestores de paquetes simplifican la instalación ya que instalan las dependencias de mysql, modifican permisos sobre archivos, etc.
    - La versión Enterprise solo está disponible para los clientes de Oracle, no hay repositorios públicos para que sean utilizados por los gestores de paquetes. Esto quiere decir que se debe descargar los archivos de manera local para instalarlos.
    - La intalación por gestor de paquetes es mucho mas simple que realizandola desde un archivo binario y configurando cada uno de los parametros.
    - __/var/lib/mysql__ es la ubicación por defecto de cualquier base de datos nueva.
    - __/user/bin__ binarios de espacio de usuario incluido el cliente mysql y otras herramientas administrativas.
    - __/etc/__ (o __/usr__) Contiene los archivos de configuración del todo el servidor (my.cnf).
    - __etc/init.d__ Usado en distribuciones que utilizan sysvinit, contiene comandos de configuración inicial. Si utiliza systemd no es necesario porque hace la configuración de una manera diferente.
    - __/var/log__ archivo legible que contiene lso errores de mysql. Tiene el mismo formato que los logs binarios o los archivos estrucutales de InnoDB.
    - Adicionalmente se pueden instalar plugins, los cuales funcionan estrechamente con el servidor y al llamar a las API expuestas por el servidor, agregan funciones al proporcionar funciones o variables adicionales. Tambien se puede interactuar con los servidores en varibales y funciones globales.
    - Los componentes estan separados del servidor y amplian su fncionalidad basandose en una arquitectura de servicios.
    - Se puede ampliar MySQL usando procedimientos almacenados, triggers, y funciones con extensiones SQL. O mediante la creación de funciones externas definidas por el usuario cargadas dinamicamente.

### Initial User Accounts
    - El identificador de cuenta MySQL es mas que un usuario y una contraseña. Consta de 3 elementos, 2 de ellos identifican a la cuenta y uno se utiliza para la autenticación.
    - username@hostname + password
    - se deben proporcionar los tres elementos para acceder a mysql.
    - El hostname es quien controla donde puede iniciar sesión el usuario. Puede ser un equipo DNS o una ip.
    - '%' permite que el usuario inicie sesión desde cualquier host o dentro de una dirección ip para limitar el acceso desde ciertas ip dentro de una red.
    - La primera vez se instalan varias cuentas de sistema. La única cuenta que puede iniciar sesión es la cuenta adminitrativa 'root'@'localhost'.
    - Por seguridad, la contraseña se debe cambiar, mysql no deja hacer ninguna acción sin antes cambiar la contraseña.
    - MySQL se ejecuta como usuario a nivel de sistema. Cada SO tiene su propio método para crear dicho usuario. En gral se utilizan los siguientes pasos (salvo windows o un RPM en Oracle linux):
        - Cada proceso de instalación crea y configura el usuario a nivel de sistema.
        - Si se hace desde un binario:
            - Se debe crear el usuario que corra el proceso mysql server
            - Se debe crear los directorios de la infraestructura.
            - Antes de iniciar, se debe configurar el servidor usando el archivo my.cnf, especificando usuario, servidor y la ubicación del directorio de datos.
            - Una vez configurados estos archivos se puede proceder con la instalación del servidor.
            - Inciar el proceso mysql server. Se pueden personalizar los script de inicio y finalización.
    - Practicas de seguridad:
        - Crear el usuario de proceso del servidor genérico sin permisos avanzados. No necesita realizar la función de adminitración del sistema. No necesita tener acceso completo al sistema de archivos. No necesita acceso a la shell. Pero si requiere acceso a los archivos del directorio de datos y de logs, como así también permisos para gestionar copias de seguridad o scripts que utilice el proceso servidor.

### Initial Configuration
Algunas veces es necesario realizar cambios de la configuración inicial. Una razón típica de este cambio es tener más control sobre la unicación de los archivos importantes.  
La variable que controla las ubicaciones de los archivos es __basedir__ y __datadir__ que es el directorio de base de datos.  
La raíz de la instación puede colocarse en cualquier lugar del sistema. Se pueden instalar varias versiones de mysql en directorios diferentes y crear un enlace simbólico para hacer referencia a cada uno.  
#### Archivo de Configuración
Socket: Especifica la ubicación del archivo de socket de Unix que los clientes locales pueden utilizar para conectarse al servidor en lugar de utilizar una conexión tcp.  
my.cnf en windows es my.ini  
Si hay errores de configuración el servidor no se ejecuta.  
Tiene valores por defecto adecuados para la mayoria de los usos.  

Si se realiza la instalación desde un archivo binario, se debe inicializar el directorio de datos ya que esto crea la base de datos del sistema e inicializa el motor de almacenamiento y los archivos de logs.  
Hay que darle permisos al usuario mysql para que el servidor tenga acceso a los archivos de base de datos.  
>$> bin/mysqld --initialize --user=mysql>  

Esto crea la cuenta root y muestra la contraseña generada en la consola. Esto es una practica insegura.  
Una vez configurado el servidor es momento de ejecutarlo. El servicio se llama _mysqld_.  
Si se desea utilizar una configuración propia para el servicio se puede cambiar el archivo por defecto modificando la variable _--defaults-file=/mysql/my.cnf_.  
Si se desea cambiar la configuración de red para el inicio de sesión, se debe usar al opción _--bind-addres_.  
Si se necesita iniciar el servicio sin ningun tipo de seguridad (por ejemplo si se olvida la contraseña de root y necesita cambiarla) se puede utilizar la opción omitir tablas de concesiones _--skip-grant-tables_.  


### Updating MySQL
Para actuzalizarlo es necesario detener el servidor. Si es necesario se deben cambiar los archivos de configuración.  
Una buena práctica es realizar un backup antes de realizar el upgrade.  
El proceso de actualización ofrece 2 opciones:  
    - Interna, utiliza el directorio de datos existente. Sustituir el paquetes con los binarios por el de las nuevas versiones, o instale los nuevos ejecutables binarios.  
    - Lógica, realizar un backup del servidor para luego instalar la nueva versión como una instlación nueva con un directorio de archivos limpio. Luego restaure la copia de seguridad.  

También es necesario actualizar los archivos de soporte que utilice su aplicación para conectarse a MySQL.  
Para la versión enterprise es la misma forma de instalar, solo que para descargarlo se tiene un url privado.  
Usando la shell se puede comporbar el cambio de versión para ello verifica que el archivo de configuración no utiliza palabras reservadas, si no se borraron tipos de datos o se cambiarlos parametros de valores por defecto o ya no existen.  
El usuario que realiza la comprobación debe tener privilegios de RELOAD, PROCESS y SELECT en el sistema.  


## SKILL CHECK: MODULO 3 
1. Which installation merhod requires that you manually configure the service user?  
The yum and RPM package installers install and configure MySQL on Linux. The MySQL Installer installs and configures MySQL on Windows. The binary archive only contains the necessary files but does not perform any configuration.  
2. Which statement is tru about upgrades?  
Upgrading is an offline operation, performed in-place by replacing existing binaries with the new version. This process also works when upgrading to Enterprise Edition. The Upgrade Checker utility is available in MySQL Shell, and can be used on any MySQL version and edition up to and including the version of MySQL Shell.  
3. Which permissions are required for the mysql servide user?  
The MySQL service user needs only privileges to run the process and access the network and relevant directories in the file system. You should not grant permissions beyond that, so that the service cannot be exploited by malicious users.  
4. Which statement is true about the data directory?  
The data directory setting datadir specifies the default location of system and user databases, and is one of the settings for file locations. Other settings include locations for temporary files and configuration files.  
5. How often are MySQL innovation versions released?  
MySQL long-term support versions are released every two years. Innovation versions are released quarterly.  
