# docker-zimbra-8_8_15-dwinar
Zimbra

Repository ini merupakan repository cara untuk install zimbra 8.8.15 pada docker

Docker

Cara Install Docker

Untuk dapat menginstall docker pada host server anda, silahkan ikuti panduan berikut: https://docs.docker.com/engine/install/

Downloading the image
The first step is to pull this image into your docker environment, for that just run the next:

docker pull jorgedlcruz/zimbra
Creating Zimbra Containers
Now that we have an image called jorgedlcruz/zimbra, we can do a docker run with some special parameters, like this:

docker run -p 25:25 -p 80:80 -p 465:465 -p 587:587 -p 110:110 -p 143:143 -p 993:993 -p 995:995 -p 443:443 -p 8080:8080 -p 8443:8443 -p 7071:7071 -p 9071:9071 -h zimbra-docker.zimbra.io --dns 127.0.0.1 --dns 8.8.8.8 -i -t -e PASSWORD=Zimbra2017 jorgedlcruz/zimbra
As you can see we tell the container the ports we want to expose, and on which port, we also specify the container hostname, the password foir the Zimbra Administrator Account, and the image to use.

That's it! You can visit now the IP of your Docker Machine using HTTPS, or try the Admin Console with HTTPS and port 7071.

Contribute to the Project
If you like to contribute to the project, you are free to do so, just fork this repo and submit your changes.

Manual process - not really recommended
Manual process
Known issues
After the Zimbra automated installation, if you close or quit the bash console from the container, the docker container might exit and keep in stopped state, you just need to run the next commands to start your Zimbra Container:

docker ps -a 
docker start YOURCONTAINERID
docker exec -it YOURCONTAINERID bash
su - zimbra
zmcontrol restart