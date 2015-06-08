## Quagga_docker_gns3

###Manage quagga docker container for use with GNS3.
------
##### Requirements:
-  [Docker](https://docs.docker.com/installation/):
-  Pipework
```
sudo bash -c "curl https://raw.githubusercontent.com/jpetazzo/pipework/master/pipework > /usr/local/bin/pipework"
```



##### Build Quagga docker image

From Dockerfile:
(sudo docker build -t {tag} {Dockerfile_location})
ex:
```
sudo docker build -t quagga .
```





##### Manage Quagga containers
- Running new container
- Start stopped containers
- Delete running/stopped container
- Configure advanced networking (For connection with GNS3)

```
./startquagga.sh {quagga_image_tag} {container_name}
```





##### Show Quagga configuration files 
(persistent after container deletion)
```
sudo ./confdir.sh
```





##### SSH to quagga container
To be able to SSH to your quagga container, put your public file “id_rsa.pub” in the current directory containing “Dockerfile”

From the container terminal, enable SSHD
```
/usr/sbin/sshd
```





##### Start quagga process
From the container terminal or SSH console, start quagga
```
/etc/init.d/quagga
```





##### Example of GNS3 configuration to connect quagga docker container:

![alt tag](http://hpnouri.free.fr/git/Selection_015.png)





##### Stop or remove all containers in Docker host:
```
sudo ./clean_docker.sh
```



##### GUI Monitoring & managing containers
```
sudo ./qmonitor.sh
```
then browse:

127.0.0.1:8080

and

127.0.0.1:10086
