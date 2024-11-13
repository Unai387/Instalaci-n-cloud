# Instalación Owncloud #
<p> sudo apt update </p>
<p> Contraseña: usuario </p>
<p> sudo apt upgrade </p>
<p> Responder si </p>
<p> sudo apt install -y apache2 </p>
<p> sudo apt install -y mysql-server </p>
<p> sudo apt install -y php libapache2-mod-php </p>
<p> sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl </p>
<p> sudo systemctl restart apache2 </p>
<p> sudo mysql </p>
<p> CREATE DATABASE bbdd; </p>
<p> CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password'; </p>
<p> GRANT ALL ON bbdd.* to 'usuario'@'localhost'; </p>
<p> exit </p>
<p> mysql -u usuario -p </p>
<p> Contraseña: password </p>
<p> sudo cp ~/Baixades/app-web.zip /var/www/html </p>
<p> cd /var/www/html </p>
<p> sudo unzip app-web.zip </p>
<p> sudo cp -R app-web/. /var/www/html </p>
<p> sudo rm -rf app-web/ </p>
<p> sudo rm -rf /var/www/html/index.html </p>
<p> sudo rm -rf /var/www/html/index.html </p>
<p> cd /var/www/html </p>
<p> sudo chmod -R 775 . </p>
<p> sudo chown -R usuario:www-data . </p>
