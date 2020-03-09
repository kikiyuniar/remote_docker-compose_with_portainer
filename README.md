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
* 
