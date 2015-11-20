# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  # forward port 9000 so grunt serve works and port 35729 so the live reload works
  config.vm.network "forwarded_port", guest: 9000, host: 9000
  config.vm.network "forwarded_port", guest: 35729, host: 35729

  # Increase the amount of memory on the virtual machine:
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  # Provisioning with a shell script. Simply put, all the commands needed 
  # to set up the virtual machine from scratch
  config.vm.provision "shell", inline: <<-SHELL
    curl -sL https://deb.nodesource.com/setup_5.x | sudo -E bash -
    sudo apt-get install -y nodejs ruby mongodb git
    npm install -g grunt-cli grunt bower
    cd /vagrant
    npm cache clear
    npm install --no-bin-links
    bower --allow-root install
    sudo gem install sass
  SHELL
end
