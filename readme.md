# Quagga_docker_gns3
Running quagga docker container for use with GNS3.

Build Quagga Docker image from Dockerfile:

sudo docker build -t <tag> <Dockerfile_location>
sudo docker build -t quagga .

Manage Quagga containers:
- Running new container
- Start stopped containers
- Delete existing container
- Configure advanced networking (For connection with GNS3)

run startquagga.sh script

./startquagga.sh <quagga_image_tag> <container_name>



Stop or remove all containers in Docker host:
sudo ./clean_docker.sh


Show Quagga configuration files (persistent after container deletion)
sudo ./confdir.sh

To be able to SSH to your quagga container, put your public file “id_rsa.pub” in the current directory containing “Dockerfile”
From the container terminal, enable SSHD
/usr/sbin/sshd

From the container terminal, start quagga
/etc/init.d/quagga


