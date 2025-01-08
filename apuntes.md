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


# 4. MySQL Database Design
## 4.1 Database Design
### Almacenamiento de Datos
La capa del motor de almacenamiento forma parte del proceso del servidor. Se interpone entre las partes del servidor responsable de introducir, analizar y optimizar SQL y los sistemas de archivos subyacentes.  
El motor de almacenamiento estándar se denomina InnoDB. También puede usar otro tipo, por ejemplo MyISAM, NDB Cluster, Memory.  
MyISAM es rápido y básico pero tiene menos funciones de fiabilidad. Mientras que NDB es un motor distribuido escalable, se ejecuta en varios nodos y utiliza software adicional para gestionar el acceso al clouster.  
InnoDB soporta concurrencia, es decir, que muchos usuarios accedan a los archivos simultáneamente y manteiene sus cambios separados entre sí. Esto se logra ya que usa transacciones. _Las transacciones permiten a los usuarios realizar cambios de los que se puede realizar un rollback si es necesario y evitar que otros usuarios vean esos cambios hasta que se confirmen o guarden de forma persistente._  
InnoDB permite la integridad referencial, esto asegura que los datos de una tabla dependiente hacen referencia a solo a datos de origen válidos. Ej: no se puede modificar un dato que no existe. No se puede cambiar la contraseña de un usuario que no existe. 
InnoDB almacena datos _raw_ en disco en una estructura de árbol B y utiliza algoritmos rápidos para insertar filas en el lugar correcto. Esto permite que los datos se puedan recuperar rápidamente.
InnoDB utiliza un método similar para almacenar índices. Esto permite ejecutar consultas en función de un orden de clasificación distinta del orden natural de las filas.  
InnoDB tiene su proprio pool de buffers, se trata de una memoria caché que almacena los datos a los que se ha accedido recientemente, con esto se obtienen lecturas de datos activos mucho mas rápidas que las consultas que se leen desde el disco.  
InnoDB cuenta con optimización de inserción masiva y multithreading.  
Por defecto en la instalación de MySQl se define InnoDB como motor de almacenamiento ya que ofrece fiabilidad y alto rendimiento. Soporta sintaxis de transacción, como confirmación y rollback, y es compatible con ACID:  
* __Atomico__: La transacción puede contener varias sentencias, pero la transación en su conjunto se trata como un cambio que se realiza correcta o incorrectamente.  
* __Consistente__: Las transacciones se mueven en el sistema de un estado consistente a otro.
* __Aislado__: Los cambios realizados durante una transacción se aíslan de otros usuarios hasta que se complete esa transacción.
* __Duradera__: El servidor garantiza que la transacción se mantenga o se escriba en el disco una vez se complete.  

InnoDb soporta cifrado de datos, lo que permite mantener los datos seguros en el disco. También soporta compresión lo que ahorra espacio al costo de un uso adicional del CPU.  
Se puede configurar un cluster InnoDb de varios nodos de servidor MySQL en varios host para habilitar la alta disponibilidad.  
El uso de transacciones es fundamental para el uso donde varios usuarios simultáneos pueden cambiar datos.   
Por defecto, cada sentencia se confirma automáticamente para que no tenga que escribir la confirmación cada vez que actualice una fila. 
START TRANSACTION es sinonimo de BEGIN cualquiera de ellas se puede utilizar como iniciar una transacción.  
DML( Lenguaje de manipulacion de datos). Dentro de una transacción no se confirma automaticamente cada sentencia, por lo que debe hacerse manualmente o realizar un rollback para deshacer la transacción. _Esto no es aplicable para DDL (lenguaje de definición de datos)_ como CREATE TABLE. DDL utiliza una confirmación implícita.  
## 4.2 Database and Tables
Tanto esquema como la base de datos hacen referencia a recopilaciones de tablas y otros objetos. En MySQl esquema es un sinónimo de base de datos, pero puede pasar que un esquema contenga una base de datos.  
En los motores de almacenamiento (incluyendo InnoDB) cada base de datos se asigna a un directorio del sistema de archivos (en gral en el directorio de datos). Cada tabla tiene datos de filas almacenados en un archivo. En innoDB este archivo se llama __tablespace__ aunque se puede almacenar las tablas en otro tablespaces.  
Las bases de datos de esquema de información y MySQL se utilizan para almacentar, presentar información estructural sobre el servidor, incluida la configuración de autenticación y los metadatos de la tabla. También es posible consultar métricas de rendimiento desde el esquema de rendimiento y las bases de datos del sistema. Si se usa un cluster con innoDB se pueden consultar los datos de metadados del cluster.  
Las columnas deben tener tipos de datos definidos.  
CHAR es una cadena de ancho fijo mientras que varchar es de ancho variable.  
ENUM y SET se usan para seleccionar un conjunto de valores definidos.  
BLOB (binary large object block) pueden contener grandes fragmentos de datos binarios. Ej: Imagenes JPG o audio MP3. 
TEXT almacena grandes cantidades de datos de texto.  
Tanto BLOB como TEXT no se almacenan en la misma ubicación que otros datos de la misma fila, esto se hace para mejorar el rendimiento porque muchas consultas en la tabla no consultan los datos blob o text incluidos en la tabla.  
MySQL soporta datos geográficos o espaciales y consultas sobre esos datos. Incluyen formas de representar puntos, lineas, polígonos y colecciones  de tales elementos.  
Los tipos de datos JSON permite utilizar a mysql como almacén de documentos. Una columna de este tipo puede contener documentos JSON completos en cada fila. Mysql tiene varias funciones que permiten consultar y buscar valores dentro de dichos documentos.  
## 4.3 Indexes
Los índices permiten mejorar el rendimiento de las consultas ya que facilitan la búsqueda de filas específicas. Esto no solo aceleara la consultas, sino que también garantiza que las filas recién insertadas se coloquen la mejor posición del archivo de datos para que las futuras consultas las encuentren rápidamente.  
Los índices funcionan almacenando los datos raw o un subjuego de los datos raw en algún orden definido. Un índice se puede ordenar en algún valor no único, como el nombre de una persona o también puede crear un índice en algún valor que debe ser único dentro de la tabla (como un ID). El índice principal, a veces llamado índice agrupado, son los datos completos de la tabla almacenados en un valor único denominado _clave primaria_.  
InnoDB soporta distintos tipos de índices. Los datos raw de la mayoría de los índices secundarios se almacenan en una estructura **BTREE**. Almacena datos en cubos específicos basados en la clave de índice mediante páginas de datos de tamaño fijo. También tiene una función HASH adaptable, que se inicia automáticamente para tablas y cargas de trabajo pequeñas que se benefician de ellas. Los datos espaciales se indexan utilizando la estructura **TRTREE**.
Buenas prácticas para los índices:
* Crear una PK en cada tabla. Este valor es único para cada fila y se utiliza para ordenar los datos de la fila. InnoDB no necesita que la tabla tenga una PK explícita, pero si no se la define crea una PK oculta.
* Cada índice secundario es una parte de los datos ordenados por otra columna. Cada entrada de índice utiliza la PK como una consulta al resto de la fila. Si la PK es grande o compleja aumenta el requerimento de almacenamiento de cada índice.
* Cada vez que se modifaca una fila mysql debe actualizar todos los índices. A más indices tiene una tabla más lenta será cada operación inserción. MYSQL Enterprise Monitor tiene funciones para identificar los índices que no se utilizan.
* Utilice prefijos y claves compuestas para reducir índices. Una clave de prefijo contiene solo la primera parte de una cadena (util cuando se tiene gran cantidad de datos). Una cable compuesta contiene varias columnas, esto acelera la búsqueda porque el índice secundario puede completar la consulta sin necesidad de volver a buscar las PK.  
__El indice secundario utiliza la PK para buscar la fila completa__.

## 4.4 Joins
Permite realizar consultas de varias tablas que cumplan cierta condición. Hay 4 tipos: inner, left, right y full. También está la opción semijoin que contiene solo los datos de una tabla.  
El comando __EXPLAIN__ permite examinar consultas y cómo las procesará mysql. Muestra las tablas e índices involucrados en la consulta, esto funciona tanto en DDL como en DML.  
## 4.5 Partitioning
Permite dividir el contenido de una tabla de acuerdo a determinadas reglas. Esto permite dividir los datos de una tabla grande en diferentes discos, como también separar aquellos datos que son accedidos frecuentemente en un almacenamiento con menor costo de lectura.  
Esta función solo es soportada en la versión Enterprise.  
## SKILL CHECK - MODULO 4
1. Wich is the default mysql storage engine?
InnoDB
2. what is performed by the join clause in sql?
The JOIN clause uses a condition to decide which row in the table named on the left side is connected to which row on the right side.  
3. Which statement is true about PRIMARY indexes?
The PRIMARY index manages the primary key of a table. Its values must be unique and are used as a lookup value for all secondary indexes. PK values are replicated to every secundary index.  
4. What can you accomplish using mysql partitioning?
MySQL Partitioning enables you to select the physical location of rows based on a rule that specifies some condition in each row.
5. Which data type stores string values?
ENUM.  

# 5. Database Security
## SKILL CHECK - MODULO 5
1. Which type of compliance do GDPR, HIPAA, FERPA, and GLBA impose that mysql can implement?
The acronyms in the question refer to legal provisions in multiple jurisdictions, all of which provide regulatory frameworks which must be complied with by applicable organizations.
2. Which product can mitigate the risk of SQL inyection attacks?
MySQL Enterprise Firewall enables you to create an allow list of statements, and it blocks statements that do not match that allow list. SQL injection attacks attempt to insert SQL statements within user interfaces, and if those statements are not in the allow list then they are prevented from executing.
3. Which statement about dynamic privileges is true?
They are assigned by the server, a plugin, or a component at load time.
Dynamic privileges are granted by the server at run time, either during the startup process or by plugins and components as they are loaded. They may also be granted explicitly with GRANT statements. They are not specified in configuration files.
4. What is a default Mysql authentication plugin used to encrypt password?
MySQL encrypts passwords before storing them in the database. The caching_sha2_password plugin uses a secure one-way encryption algorithm to create passwords that cannot easily be decrypted, even if the database is compromised.
5. Which mysql enterprise feature supports kerberos, pam and fido?
MySQL Enterprise Authentication brings together a set of plugins that support authentication with external infrastructure based on LDAP, Kerberos, or using the Pluggable Authentication Module (PAM) framework in Linux.

# 6. Enterprise Security Tools
## SKILL CHECK - MODULO 6
1. Against what does mysql enterprise firewall provide real-time protection?
SQL injection is one of the most common and dangerous attacks a database could face. MySQL Enterprise Firewall is an application-level firewall that protects the MySQL Server against such an attack by permitting or denying SQL statement execution based on matching against lists of accepted statement patterns.
2. What file can you encrypt using mysql enterprise transparent data encryption (TDE)?
MySQL stores table data in a tablespace file. Using MySQL Enterprise Transparent Data Encryption (TDE), you can encrypt these files to protect the privacy of your information, prevent data breaches and help meet regulatory requirements. TDE can also encrypt log files such as binary, relay, undo, and redo logs, but it cannot encrypt general query, slow query, and error log file.
3. Which two formatting options are supported by mysql enterprise audit?
The supported audit log file formats are XML and JSON. The default is XML. However, this can be changed at server startup by setting the audit_log_format variable.
4. When using mysql TDE, which key must be stored outside the database?
InnoDB uses a two-tier encryption key architecture, consisting of a master key and tablespace keys. When a tablespace is encrypted, a tablespace key is encrypted and stored in the tablespace header. InnoDB uses a master encryption key to decrypt the tablespace key when accessing encrypted data. It is the master key that must be stored outside the database (in a key vault) and should be rotated periodically or whenever you suspect that the key has been compromised and this key.
5. In which two ways can you install the mysql enterprise masking and de-identification feature?
MySQL Enterprise Masking and De-Identification feature can be implemented through either a plugin or a component. Plugins are a set of loadable functions that provide a SQL-level API for performing operations such as masking and de-identification. Components are self-contained code containers that interact with other code exclusively by implementing and consuming services via the registry. However, enabling both at the same time is unsupported and results may not be as anticipated.

# 7. MySQL BACKUP
## 7.1 Backups type
* Bakcup Logico: Es un script que contiene secuencias SQL. Se puede hacer con mysqldump, mysqlshell o data export (exporta la información en formato cvs).
* Backup Físico: Consiste en copiar los archivos del sistema de archivos, por ejemplo el spacetables (archivo que contiene la información de las tablas).
* Se pueden hacer backups completos que contiene una imagen fisica y lógica de toda la base de datos, esta demora demasiado tiempo en compleatarse y restaurarse. 
* Backup Incremental, solo contiene los cambios realizados desde el último backup completo. Estos cambios los obtiene de los archivos log binarios. Para restaurar este tipo de bk es necesario restaurar el bk completo y cualquier bk incremental anterior a este.
## 7.2 Adventages and Disadventages
* Snapshot: Es rápido. Suele ser una función del sistema de archivos subyacente (por ejemplo del SO). Desventajas:-- El snapshot puede realizarse mientras se está ejecutando una transacción, por lo que puede causar inconsistencias. Para evitar es neceario parar el servicio al momento de hacer el snap. Es una copia del sistema de archivos no de la base de datos en sí. El acumular snap ocupa espacio y se ve afectada las operaciones de escritura, por lo que es recomendable borrar aquellas que ya no estén en uso. No son adecuadas para mover bk entre sistemas.