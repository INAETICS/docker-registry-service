Docker Registry Service
=======================

Run [Docker Registry](https://github.com/dotcloud/docker-registry) as a CoreOS/Docker service.

Run on localmachine
-------------------

* Install Docker
* Clone this repository
* Run `./docker-registry-service run`
* Check `http://localhost:5000/v1/search`


Run in Vagrant
--------------
* Install Vagrant & VirtualBox
* Clone this repository
* Configure discovery in coreos-userdata (optional)
* Run `vagrant up`
* Check `http://172.17.8.100:5000/v1/search`

