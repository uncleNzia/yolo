# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/ubuntu2004"
  config.vm.hostname = "IP3"
  config.vm.network "private_network", type: "dhcp"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"  # Set the amount of RAM for the VM (adjust as needed).
    vb.cpus = 2 
  end  
  
# Provisioning configuration for Ansible.
config.vm.provision "ansible" do |ansible|
ansible.playbook = "playbook.yml"
end
end
