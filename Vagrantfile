# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    
  config.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.memory=1024
      vb.cpus=1
      vb.check_guest_additions=false
  end
  config.vm.box_check_update=false
  config.vm.box="ubuntu/focal64"

 
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end

  config.vm.define "web" do |web|
    web.vm.hostname = "web"
    web.vm.network "private_network", ip: "192.168.1.2"
  end

  config.vm.define "db" do |db|
    db.vm.hostname = "db"
    db.vm.network "private_network", ip: "192.168.1.3"
  end
end
