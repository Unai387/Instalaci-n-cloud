# Configuración clouds #
<h2> Explicare paso a paso como realizar la configuración de la Owncloud </h2>
<h3> Paso 1 </h3>
<h3> Actualizar la maquina </h3>
<h4> Utilizaremos los siguientes comandos para actualizar la maquina </h4>
<h3> sudo apt update </h3>
<p> Despues de ejecutar el comando sudo apt upgrade nos pedira una contraseña, la cual es Usuario </p>
<img src="Captura de pantalla 2024-11-13 215646.png" alt="Contraseña update">
<h3> sudo apt upgrade </h3>
<p> Cuando ejecutemos el siguiente comando nos pedira responder s o n, responderemos s, que es si</p>
<img src="Captura de pantalla 2024-11-13 215800.png" alt="Pregunta upgrade">
<h3> Paso 2 </h3>
<h3> Instalar apache2 </h3>
<p> sudo apt install -y apache2 </p>
<h3> Paso 3 </h3>
<h3> Instalar mysql </h3>
<p> sudo apt install -y mysql-server </p>
<p> Al momento de ejecutar nos pedira la contraseña, es Usuario</p>
<h3> Paso 4 </h3>
<h3> Instalaremos las librerías </h3>
<p> Para instalar las librerías utilizaremos los siguientes dos comandos </p>
<ul> 
<li> sudo apt install -y php libapache2-mod-php </li>
<li> sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl </li>
</ul>
<h3> Paso 5 </h3>
<h3> Reiniciamos el servidor apache2 </h3>
<p> Utilizaremos el siguiente comando: sudo systemctl restart apache2 </p>
<h2> Ahora configuraremos el Mysql </h2>
<h3> Abriremos el mysql </h3>
<p> Utilizaremos el comando sudo mysql </p>
<h3> A continuación crearemos la base de datos, un usuario y daremos privilegios a el usuario </h3>
<p> Utilizaremos estos comandos en orden </p>
<ul>
  <li> CREATE DATABASE bbdd; </li>
  <li> CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password'; </li>
  <li> GRANT ALL ON bbdd.* to 'usuario'@'localhost'; </li>
</ul>
<p> Saldremos del mysql utilizando el comando exit </p>
<h3> Probaremos la conexión de la base de datos </h3>
<p> mysql -u usuario -p </p>
<img src="Captura de pantalla 2024-11-13 221137.png" alt="Conexión base de datos">
<p> La contraseña es "password" </p>
<h3> Instalaremos la cloud </h3>
<p> Instalaremos la Owncloud desde este enlace: </p>
<a href="https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip">Instalar Owncloud</a>
<p> Despues de descargar la Owncloud le cambiaremos el nombre a app-web, seguidamente utilizaremos el siguiente comando: sudo cp ~/Baixades/app-web.zip /var/www/html</p>
<p> Cambiaremos la palabra "Baixades" por "Descargas" </p>
<h3> Entraremos al directorio </h3>
<p> Con el comando cd /var/www/html </p>
<h3> Descomprimimos el fichero </h3>
<p> Utilizaremos el comando sudo unzip app-web.zip </p>
<p> Esto lo que hará es descomprimir el archivo </p>
<p> Copiaremos los ficheros dentro de la carpeta html utilizando el comando sudo cp -R app-web/. /var/www/html </p>
<p> El nombre de app-web abría que cambiarlo por el nombre de la carpeta creada anteriormente, el cual es Owncloud </p>
<p> Borraremos la carpeta que s eha creaod cuando hemos hecho el unzip con este comando: sudo rm -rf app-web/</p>
<p> Borramos el archivo index.html con este comando: sudo rm -rf /var/www/html/index.html </p>
<h3> Damos permisos a las aplicaciones webs </h3>
<p> Utilizando los siguientes comandos </p>
<ul> 
  <li> cd /var/www/html </li>
  <li> sudo chmod -R 775 . </li>
  <li> sudo chown -R usuario:www-data . </li>
 </ul>
 <h3> Actualizar la versión de 7.4 de PHP en Ubuntu </h3>
 <p> Instalaremos los requisitos previos de PPA, con el siguiente comando: sudo apt install software-properties-common -y </p>
 <p> Instalamos las herramientas necesarias para trabajr con archivos PPA </p>
 <p> LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y </p>
 <p> Actualizamos los repositorios: sudo apt update </p>
 <p> Instalamos las librerías </p>
 <ul>
   <li> sudo apt install php7.4 -y </li>
   <li> sudo apt install -y php libapache2-mod-php7.4 </li>
   <li> sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl </li>
 </ul>
 <p> Seleccionamos la versión que queremos instalar, que en este caso sería la 7.4 </p>
 <p> Activamos los módulos necesarios </p>
 <ul>
   <li> sudo a2enmod proxy_fcgi setenvif </li>
   <li> sudo a2enconf php7.4-fpm </li>
 </ul>
 <p> Reinciamos el apache con este comando: "sudo service apache2 restart" y ya podriamos inciar sesión en el Owncloud </p>
 <p> Por último entramos a la owncloud y ponemos los siguientes datos </p>
 <a href="http://localhost/">hhtp://localhost.com</a>
<p> Ponemos los siguientes datos: </p>
<ul>
  <li> Usuario: Usuario </il>
  <li> Contraseña: Password </li>
  <li> Base de datos: bbdd </li>
  <li> Dominio: localhost </li>
</ul>
