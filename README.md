# remote_docker-compose_with_portainer
easy way of remote docker-compose using Portainer.io docker management with on one network.

Post in Linkedin : https://www.linkedin.com/in/kikiyuniar/

Aku *sedang* belajar **menulis** dengan [markdown](https://en.wikipedia.org/wiki/Markdown).

Langkah pertama yang harus dilakukan adalah :
*install portainer di dalam satu container.
example:

```java
$ docker run -d -p 860:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer
```

*buat docker-compose yang ingin digunakan dan di akses didalam satu jaringan
*
