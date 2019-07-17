# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.hostname = "oradb"
  config.vm.network "private_network", ip: "10.0.0.10"
  
  # config.hostmanager.enabled = true
  # config.hostmanager.ignore_private_ip = false  
  
  config.vm.provider "virtualbox" do |vb|
		vb.gui = false
		vb.name = "Oracle12c"
		vb.memory = 2048
		vb.cpus = 2
  end

	config.vm.provision "ansible" do |ansible|
    ansible.playbook = "oracle-db.yml"
    ansible.inventory_path = "./hosts"
    ansible.limit = 'all'
  end
end
