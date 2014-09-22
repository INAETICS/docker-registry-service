# -*- mode: ruby -*-
# # vi: set ft=ruby :

require 'fileutils'
Vagrant.require_version ">= 1.6.0"

$instance_name="docker-registry-service"
$instance_ip="172.17.8.120"

$coreos_channel="alpha"
$coreos_name="coreos-" + $coreos_channel 
$coreos_version=">= 361.0.0"

$virtualbox_gui = false
$virtualbox_memory = 2048
$virtualbox_cpus = 1

Vagrant.configure("2") do |config|

  config.vm.box = $coreos_name
  config.vm.box_version = $coreos_version
  config.vm.box_url = "http://" + $coreos_channel + ".release.core-os.net/amd64-usr/current/coreos_production_vagrant.json"

  config.vm.define vm_name = $instance_name do |config|

    config.vm.hostname = vm_name
    config.vm.network :private_network, ip: $instance_ip

    config.vm.provider :virtualbox do |virtualbox|
      virtualbox.gui = $virtualbox_gui
      virtualbox.memory = $virtualbox_memory
      virtualbox.cpus = $virtualbox_cpus
    end

    # Provision with NFS
    # config.vm.synced_folder ".", "/var/lib/docker-registry-service", id: "docker-registry-service", :nfs => true, :mount_options => ['nolock,vers=3,udp']

    # Provision service with shell
    # config.vm.provision :file, :source => ".", :destination => "/tmp/docker-registry-service"
    # config.vm.provision :shell, :inline => "rm -rf /var/lib/docker-registry-service; mv /tmp/docker-registry-service /var/lib/docker-registry-service", :privileged => true

    #Provision userdata with shell
    config.vm.provision :file, :source => "coreos-userdata", :destination => "/tmp/vagrantfile-user-data"
    config.vm.provision :shell, :inline => "mv /tmp/vagrantfile-user-data /var/lib/coreos-vagrant/", :privileged => true
  end
end
