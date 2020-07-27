# -*- mode: ruby -*-
# vi: set ft=ruby :

# README
#
# Getting Started:
# 1. vagrant plugin install vagrant-hostmanager
# 2. vagrant up
# 3. vagrant ssh
#
# This should put you at the control host
#  with access, by name, to other vms

#unless Vagrant.has_plugin?("vagrant-vbguest")
  #puts 'Installing vagrant-vbguest Plugin...'
  #system('vagrant plugin install vagrant-vbguest')
#end

unless Vagrant.has_plugin?("vagrant-hostmanager")
    puts 'Installing vagrant-hostmanager Plugin...'
    system('vagrant plugin install vagrant-hostmanager')
end

  Vagrant.configure(2) do |config|
    config.hostmanager.enabled = true
  
    config.vm.box = "centos/7"
  
    config.vm.define "MogoCentos", primary: true do |h|
      h.vm.hostname = "MogoCentos"
      h.vm.network "private_network", ip: "192.168.56.102"
      # dar instrucciones de instalación de docker desde shell
      # h.vm.provision :shell, path: "docker_install_script.sh"
      h.vm.provider "virtualbox" do |vb|
        vb.memory = "4096"
      end
    end
  end
  
