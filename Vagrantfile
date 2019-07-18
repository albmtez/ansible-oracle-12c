# -*- mode: ruby -*-
# vi: set ft=ruby :

# VM memory.
vm_memory = 2048
# VM number of cpus.
vm_cpus = 2

Vagrant.configure(2) do |config|

  config.vm.define "Oracle12c" do |oracle|
    oracle.vm.box = "centos/7"
    oracle.vm.hostname = "oradb"
    oracle.vm.network "private_network", ip: "10.0.0.10"

    # oracle.hostmanager.enabled = true
    # oracle.hostmanager.ignore_private_ip = false

    oracle.vm.provider :virtualbox do |vb|
      vb.name = "Oracle12c"
      vb.gui = false
      vb.memory = "#{vm_memory}"
      vb.cpus = "#{vm_cpus}"
    end

    oracle.vm.provider :libvirt do |libvirt|
      libvirt.default_prefix = "ansible"
      libvirt.memory = "#{vm_memory}"
      libvirt.cpus = "#{vm_cpus}"
    end

    oracle.vm.provision "ansible" do |ansible|
      ansible.playbook = "oracle-db-yml"
      ansible.inventory_path = "./hosts"
      ansible.limit = 'all'
    end
  end
end
