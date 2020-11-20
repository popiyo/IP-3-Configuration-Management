# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/groovy64"
  config.vm.network :private_network, ip: "192.168.60.10"
  config.vm.hostname = "e-commerce"
  config.ssh.insert_key = false
  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.provider :virtualbox do |v|
    v.memory = 1024
  end



  # Ansible provisioning.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
