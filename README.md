# Creación del contenedor

IMPORTANTE: Antes de seguir deberemos tener instalado:
- docker: https://docs.docker.com/install/
- docker-compose: https://docs.docker.com/compose/install/

## Pasos a Seguir


1. Crear la carpeta del para el contenedor y entrar en ella

```
mkdir hackathon
cd hackathon
```

2. Clonar el repositorio

```
git clone https://gitlab.com/adga137/hackathon.git .
```

3. El siguiente paso es contruir el contenedor y ejemcutarlo para hacer este proceso se requieren permisos de administrador (root) en linux

```
docker-compose up --build
```

4. Una vez en ejecución el proyecto abrir una instancia de la terminal o consola como (root) en linux para acceder al bash del contenedor

```
docker exec -it hackathon_php-fpm bash
```

5. Una vez dentro de la bash del proyecto estaremos en la carpeta "~/src" si necesitamos composer podemos ejecutar:

```
composer install
```

5. Una vez dentro de la bash del proyecto estaremos en la carpeta "~/src" si necesitamos composer podemos ejecutar:

```
composer install
```
Al momento que se creo el proyecto se ejecutaron los comando:

```
cd ~/metazooie
composer require "acacha/admin-lte-template-laravel"
php artisan vendor:publish --tag=adminlte --force

composer require --dev laravel/dusk
php artisan dusk:install

composer require "wnx/laravel-stats" --dev
php artisan vendor:publish --provider="Wnx\LaravelStats\StatsServiceProvider"

composer require tymon/jwt-auth
php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"
php artisan jwt:secret

composer require yajra/laravel-datatables-oracle
php artisan vendor:publish --provider="Yajra\DataTables\DataTablesServiceProvider"
```
Documentación de API laravel

```
composer require "darkaonline/l5-swagger"
```

6. Una vez terminadas toda la contrucción del proyecto cada vez que querramos ejecutarlo solo debemos ejecutar:

```
docker-compose up
```

7. Parar la ejecución del contenedor pulsar teclas en la consola de ejecución "Ctrl + c"

8. Para acceder al servicio web del contenedor utilizar el navegador web traves de la siguiente URL:

Backend
```
http://localhost:820 
```
Frontend
```
http://localhost:8201
```
PHPMyAdmin
```
http://localhost:8333
```

Nota: para eliminar la imagen o contenedor se debe ejecutar:

```
docker rmi hackathon_php-fpm
docker rmi hackathon_nginx
docker rmi hackathon_mariadb
```

Eliminar Contenedores
```
docker container rm idcontenedor
```

Para consultar la lista de imagenes de contenedores ejecutar:
```
docker images
```

Para consultar la lista de contenedores:
```
docker ps -a
```
