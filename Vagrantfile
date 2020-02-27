
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.define "web_01" do |web|
  web.vm.network "private_network", ip: "192.168.200.3"
  web.vm.provision "shell", path: "script.sh"
  web.vm.network "forwarded_port", guest: 80, host: 8080
  web.vm.synced_folder "./web01", "/var/www/html"
  config.vm.provider :virtualbox do |vb|
	  vb.customize ['modifyvm', :id, '--memory', '386']
          vb.customize ['modifyvm', :id, '--cpus', '1']
          vb.customize ['modifyvm', :id, '--name', 'web_11']
          vb.customize ['modifyvm', :id, '--cpuexecutioncap', '100'] 
          end
  end
  config.vm.define "web_02" do |web|
  web.vm.network "private_network", ip: "192.168.200.3"
  web.vm.provision "shell", path: "script.sh"
  web.vm.network "forwarded_port", guest: 80, host: 8008
  web.vm.synced_folder "./web02", "/var/www/html"
  config.vm.provider :virtualbox do |vb|
          vb.customize ['modifyvm', :id, '--memory', '386']
          vb.customize ['modifyvm', :id, '--cpus', '1']
          vb.customize ['modifyvm', :id, '--name', 'web_22']
          vb.customize ['modifyvm', :id, '--cpuexecutioncap', '50']
          end
  end


end
