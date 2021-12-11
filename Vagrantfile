# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "destkop1" do |desktop1|
    desktop1.vm.box = "ubuntu/bionic64"

  end
  config.vm.define "desktop2" do |desktop2|
    desktop2.vm.box = "debian/buster64"
  end
end

=begin 
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = "2"
  end
end
=end