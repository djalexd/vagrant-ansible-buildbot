# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"
 
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
 
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "buildbot.yaml"
    ansible.extra_vars = "vars.yaml"
    ansible.inventory_path = "ansible_hosts"
    ansible.verbose = "vvvv"
    ansible.sudo = true
    ansible.limit = "all"
  end
end
