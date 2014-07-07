Docker Registry Service
=======================

Run a local [Docker Registry](https://github.com/dotcloud/docker-registry) as a
CoreOS/Docker service. This allows one to create private or testing images for
use in Docker.

Run on local machine using Docker
---------------------------------
* [Install Docker](https://docs.docker.com/installation/);
* Clone this repository: `git clone https://github.com/INAETICS/docker-registry-service.git`;
* Make sure the image is up-to-date: `./docker-registry-service build`
* Start the image by running: `./docker-registry-service start`;
* Verify that the service is up and runnin by going to "http://localhost:5000/v1/search", or check the output of "docker ps" and "docker logs".


Run in Vagrant
--------------
* Install Vagrant & VirtualBox
* Clone this repository
* Configure discovery in coreos-userdata (optional)
* Run `vagrant up`
* Check `http://172.17.8.100:5000/v1/search`

