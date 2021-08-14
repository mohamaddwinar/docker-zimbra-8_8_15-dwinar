# Docker zimbra 8.8.15 Dwinar

# Zimbra

Repository ini merupakan repository cara untuk install zimbra 8.8.15 pada docker

# Docker

Cara Install Docker

Untuk dapat menginstall docker pada host server anda, silahkan ikuti panduan berikut: https://docs.docker.com/engine/install/

# Downloading image

Langkah pertama silahkan pull image yang telah saya buat ke environment docker anda, dengan menggunakan perinah berikut:

docker pull dwinar08/docker-zimbra-8_8_15-dwinar

# Membuat Zimbra Containers

Sekarang anda sudah mempunyai image dwinar08/docker-zimbra-8_8_15-dwinar, untuk dapat dijalankan pada container docker, silahkan gunakan perintah berikut:


docker run -p 25:25 -p 80:80 -p 465:465 -p 587:587 -p 110:110 -p 143:143 -p 993:993 -p 995:995 -p 443:443 -p 8080:8080 -p 8443:8443 -p 7071:7071 -p 9071:9071 -h webmail.dwinar.web.id --dns 127.0.0.1 --dns 8.8.8.8 -i -t -e PASSWORD=password dwinar08/docker-zimbra-8_8_15-dwinar

Silahkan sesuaikan bagian hostname, password, dan port mapping sesuai dengan kebutuhan anda.

Untuk ujicoba silahkan akses ip host docker anda, untuk akses pada dashboard admin bisa menggunakan port 7071. 