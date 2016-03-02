# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define :testvm do |testvm|
    testvm.vm.box = "precise32"
    testvm.vm.network :private_network, ip: "192.168.33.22"
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible/blog.yml"
    ansible.verbose = "vvv"

  end

  config.vm.provider :virtualbox do |vbox|
    vbox.customize ["modifyvm", :id, "--memory", "1024"]
  end
end
