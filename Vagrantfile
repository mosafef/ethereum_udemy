# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "https://vagrantcloud.com/ubuntu/trusty64"
  config.vm.provider "virtualbox" do |vb|
        vb.memory = "2048" 
  end
  config.ssh.forward_x11 = true
  config.vm.network "forwarded_port", guest: 8545, host: 8545    
  
  config.vm.provision :ansible, playbook: "provisioning/playbook.yml"

  #configure consul nodes
  #config.vm.define "consul1" do |consul|
  #   consul.vm.hostname = "consul1"
  #   consul.vm.network :private_network, ip: "10.0.5.10"
  #end

  #config.vm.define "consul2" do |consul|
  #   consul.vm.hostname = "consul2"
  #   consul.vm.network :private_network, ip: "10.0.5.11"
  #end


  #config.vm.network "forwarded_port", guest: 8081, host: 8081
  
  #config.vm.provision "ansible" do |ansible|
  #   ansible.playbook = "playbook.yml" 
  #end
end
