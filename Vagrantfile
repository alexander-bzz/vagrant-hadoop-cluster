# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "CentOS-6.4-x86_64" #http://developer.nrel.gov/downloads/vagrant-boxes/CentOS-6.4-x86_64-v20130731.box

  config.vm.provision :shell, :inline => "sudo cp /vagrant/files/etc/hosts /etc/hosts"

  config.vm.define :manager do |manager_config|
    manager_config.vm.host_name = "hadoop-manager"
    manager_config.vm.network :hostonly, "192.168.56.2"
    manager_config.vm.forward_port 8080, 9999
  end

  config.vm.define :node01 do |node01_config|
    node01_config.vm.host_name = "hadoop-node01"
    node01_config.vm.network :hostonly, "192.168.56.3"
    node01_config.vm.customize ["modifyvm", :id, "--memory", 2048]
  end

  config.vm.define :node02 do |node02_config|
    node02_config.vm.host_name = "hadoop-node02"
    node02_config.vm.network :hostonly, "192.168.56.4"
    node02_config.vm.customize ["modifyvm", :id, "--memory", 2048]
  end

  config.vm.define :node03 do |node03_config|
    node03_config.vm.host_name = "hadoop-node03"
    node03_config.vm.network :hostonly, "192.168.56.5"
    node03_config.vm.customize ["modifyvm", :id, "--memory", 2048]
  end
end
