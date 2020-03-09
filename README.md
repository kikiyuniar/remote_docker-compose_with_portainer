# remote_docker-compose_with_portainer
easy way of remote docker-compose using Portainer.io docker management with on one network.

Post in Linkedin : https://www.linkedin.com/in/kikiyuniar/

Aku *sedang* belajar **menulis** dengan [markdown](https://en.wikipedia.org/wiki/Markdown).

Langkah pertama yang harus dilakukan adalah 
* install [portainer](https://www.portainer.io/) di dalam satu container.
example:

```html
$ docker run -d -p 860:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```
>catatan: 860 merupakan port yang akan di akses untuk membuka halaman portainer yang telah terpasang

* buat docker-compose yang ingin digunakan dan di akses didalam satu jaringan
example:

```yml
nginx:
    image: nginx:latest
    ports:
        - '90:80'
    volumes:
        - ./nginx:/etc/nginx/conf.d
        - ./logs/nginx:/var/log/nginx
        - ./wordpress:/var/www/html
    links:
        - wordpress
    restart: always

mysql:
    image: mariadb
    ports:
        - '3306:3306'
    volumes:
        - ./db-data:/var/lib/mysql
    environment:
        - MYSQL_ROOT_PASSWORD=aqwe123
    restart: always

wordpress:
    image: wordpress:4.9.6-php7.2-fpm
    ports:
        - '9000:9000'
    volumes:
        - ./wordpress:/var/www/html
    environment:
        - WORDPRESS_DB_NAME=wpdb
        - WORDPRESS_TABLE_PREFIX=wp_
        - WORDPRESS_DB_HOST=mysql
        - WORDPRESS_DB_PASSWORD=aqwe123
    links:
        - mysql
    restart: always

```
* 
