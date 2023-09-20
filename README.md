# pdns
How to Install and Deploy PDNS and PDNS-RECURSOR on Rocky 8.7

PowerDNS es un software opensource para el manejo de solicitudes DNS no solo como un "authoritative nameserver" sino tambien como un "DNS recursor" o dns cache.
De igual manera este software nos permite manejar un alta cantidad de peticiones por segundo, y se puede utilizar con distintos tipos de backend como BIND o  base de datos estructuradas como MySQL, PostgreSQL o Oracle Db.
EN nuestro caso utilizaremos como backend MySQL. 

En los primeros pasos pueden encontrar como instalar PDNS como un "authoritative nameserver" o servidor autoritario y luego procederemos a instalar PDNS-RECURSOR como software para el manejo de DNS CACHE.

1) Instalando y Configurando MariaDB: por defecto en los repos de rocky se encuentra mariadb asi que solo ejecuta lo siguiente:
 dnf install mariadb-server

![image](https://github.com/acosta9/pdns/assets/6999329/53565470-a07a-4aac-899a-207df2e66f6a)

  Despues de instalado procedemos a activar e iniciar el servicio de MariaDb:
  
  systemctl enable --now mariadb

  Procedemos a ejecutar el siguiente comando: (esto nos ayudara a realizar una configuracion inicial de nuestro servicio de mariadb solo sigue el wizard luego de ejecutar el comando):
  
  /usr/bin/mysql_secure_installation
  
  Set up the MariaDB root password? Input y to confirm and type the new password for your MariaDB server, then repeat the password.
  Disable remote login for the MariaDB root user? Input y to confirm and disable it.
  Remove the default anonymous user from the MariaDB? Input y to confirm.
  Remove the default database test from MariaDB? Input y again to confirm.
  Lastly, reload tables privileges to apply new changes? Input y to confirm and the MariaDB will reload all privileges and apply new settings.
2) 
