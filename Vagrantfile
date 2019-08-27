# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = "2"
  end

  config.vm.synced_folder ".", "/vagrant", mount_options: ['dmode=775','fmode=666']
  config.vm.network "public_network", bridge: "en0: Wi-Fi (AirPort)"

  config.vm.provision "shell", inline: <<-SHELL
    sudo timedatectl set-timezone Asia/Tokyo

    apt-get update
    apt-get install -y apache2
  SHELL
end
