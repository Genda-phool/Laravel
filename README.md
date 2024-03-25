docker build -t lara .

docker run -d --name mysql -e MYSQL_DATABASE=laravel -e MYSQL_USER=zain -e MYSQL_PASSWORD=zain -e MYSQL_ROOT_PASSWORD=zain -v mysql_data:/var/lib/mysql -p 3306:3306 mysql


docker run -d --name phpmyadmin --link mysql:db -p 8080:80 -e PMA_HOST=db -e MYSQL_ROOT_PASSWORD=zain phpmyadmin/phpmyadmin


docker run -d --name laravel --link mysql:db -p 8000:80 -v "$(pwd)":/var/www/html lara




