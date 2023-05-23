# Laravel Docker Container

Este contenedor está configurado y probado para correr un proyecto de Laravel y funcionar con:
 - Ubuntu 18.04
 - Nginx
 - php 7.2
 - MySQL

## Requerimientos

- Tener instalado docker
- Tener instalado docker-compose

## Instrucciones

- Clonar el repositorio
- Agregar el "Virtual host" para el proyecto
  - En Linux: `sudo nano /etc/hosts`
  - En el archivo hosts agregar: `127.0.0.1       laravel.local`
- Copiar el repositorio clonado (Docker, docker-compose.yml, Dockerfile) dentro de tu proyecto laravel
- En la terminal ir al proyecto laravel y levantar el servicio con el comando

`sudo docker-compose up`

- El proyecto ya debería estar ejecutandose en http://laravel.local/


## Configuraciones opcionales (Personalización)
### Cambiar el host del contenedor
- Abrir el archivo docker-compose.yml
- Cambiar el valor del **VIRTUAL_HOST** por el de tu preferencia
- El nuevo host debe estar registrado en (para linux: "/etc/hosts")

### Configurar el php.ini
- Abrir el archivo php/php.ini del repositorio clonado y ajustar de acuerdo a las necesidades del proyecto

### Configurar el site.conf del nginx
- Abrir el archivo nginx/site.conf del repositorio clonado y ajustar de acuerdo a las necesidades del proyecto


## Complemento

### Nginx Proxy
Este contenedor funciona con la Network **nginx-proxy** del repositorio:

https://github.com/the-aleman/proxy-nginx-docker

_______
### MySQL
Si necesitas una Base de Datos MySQL puedes usar el contenedor del repositorio:

https://github.com/the-aleman/mysql-docker

Tener en cuenta esta configuración del archivo **.env** si está usando el contenedor docker de mysql anteriormente mencionado

DB_CONNECTION=mysql  
DB_HOST=**mysql_57**  
DB_PORT=3306  
DB_DATABASE=laravel  
DB_USERNAME=root  
DB_PASSWORD=secret  
_______

### Redis
Si necesitas Redis puedes usar el contenedor del repositorio:

https://github.com/the-aleman/redis-docker