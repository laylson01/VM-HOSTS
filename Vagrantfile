#teste
# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<-EOF
    sudo apt-get update && apt-get upgrade -y 
    sudo apt install nginx -y && apt install gcc make pearl
    sudo apt autoremove
EOF



Vagrant.configure("2") do |config|
  config.vm.define "host1" do |host1|
    host1.vm.box = "ubuntu/bionic64"
    host1.vm.network "private_network", ip: "192.168.0.12"
    config.vm.synced_folder ".", "/vagrant" 

    config.vm.provision "shell", inline: $script

  end
  
  config.vm.define "host2" do |host2|
    host2.vm.box = "debian/buster64"
    host2.vm.network "private_network", ip: "192.168.0.13"
    config.vm.synced_folder ".", "/vagrant"

    config.vm.provision "shell", inline: "sudo apt update && sudo apt install nginx -y"


  end
end




=begin TESTE/BUG5151 =end

config.vm.synced_folder "../data", "/vagrant_data"
config.vm.synced_folder "../data", "/vagrant_data"

=begin 
Vagrant.configure("2") do |config|
  config.vm.box = "debian/buster64"
  config.vm.provider "test" do |tst|
    vb.memory = "1024"
    vb.cpus = "5"
  end
end
=end