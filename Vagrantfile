# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure("2") do |config|

  # config.vm.define "jenkins" do |jenkins|
  #   #Les paramètres de base de la box
  #   jenkins.vm.box = "ubuntu/trusty64"
  #   jenkins.vm.box_url = "https://atlas.hashicorp.com/ubuntu/boxes/trusty64"
  #
  #   jenkins.vm.network "private_network", ip: "192.168.33.10"
  #
  #   # La partie provisionning de la VM
  #   jenkins.vm.provision "file", source: "jenkins/Dockerfile", destination: "/vagrant/Dockerfile"
  #   jenkins.vm.provision "shell", path: "jenkins/bootstrap-ci-server.sh"
  #
  #   # Le forwarding de ports, ici on utilise le 4040 car le 8080 est fréquemment occupé par d'autres applications si l'on considère que le host est notre machine physique
  #   jenkins.vm.network "forwarded_port", guest: 49001, host: 49001
  #
  #   jenkins.vm.provider :virtualbox do |vb|
  #     vb.customize ["modifyvm", :id, "--ioapic", "on"]
  #     vb.customize ["modifyvm", :id, "--memory", "2048"]
  #     vb.customize ["modifyvm", :id, "--cpus", "2"]
  #   end
  # end

  config.vm.define "production" do |production|
    production.vm.box = "ubuntu/trusty64"
    production.vm.provision "shell", path: "production/bootstrap-production.sh"
    # tests.vm.network "private_network", ip: "192.168.33.11"

    production.vm.provider :virtualbox do |vb|
      vb.customize ["modifyvm", :id, "--ioapic", "on"]
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Define a Vagrant Push strategy for pushing to Atlas. Other push strategies
  # such as FTP and Heroku are also available. See the documentation at
  # https://docs.vagrantup.com/v2/push/atlas.html for more information.
  # config.push.define "atlas" do |push|
  #   push.app = "YOUR_ATLAS_USERNAME/YOUR_APPLICATION_NAME"
  # end
end
