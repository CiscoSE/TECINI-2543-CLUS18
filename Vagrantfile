# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.provision "shell", inline: <<-SHELL
    sudo yum install -y epel-release
    sudo yum install -y git python-pip
    yes | sudo pip install ansible ucsmsdk pylint
    git clone https://github.com/CiscoSE/TECINI-2543-CLUS18
    cd TECINI-2543-CLUS18/ansible
    git clone https://github.com/ciscoucs/ucsm-ansible
    cd ../..
    chown -R vagrant:vagrant .
  SHELL
end
