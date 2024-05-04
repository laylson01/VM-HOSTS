# Vagrantfile para criar duas máquinas virtuais: host1 e host2

# Script de provisionamento a ser executado em ambas as máquinas
$script = <<-EOF
  sudo apt-get update && sudo apt-get upgrade -y
  sudo apt install nginx gcc make -y
  sudo apt autoremove -y
EOF

# Configuração do Vagrant
Vagrant.configure("2") do |config|
  # Configuração da máquina host1
  config.vm.define "host1" do |host1|
    host1.vm.box = "ubuntu/bionic64"
    host1.vm.network "private_network", ip: "192.168.0.12"
    config.vm.synced_folder ".", "/vagrant"

    # Provisionamento da máquina host1
    host1.vm.provision "shell", inline: $script
  end

  # Configuração da máquina host2
  config.vm.define "host2" do |host2|
    host2.vm.box = "debian/buster64"
    host2.vm.network "private_network", ip: "192.168.0.13"
    config.vm.synced_folder ".", "/vagrant"

    # Provisionamento da máquina host2
    host2.vm.provision "shell", inline: "sudo apt update && sudo apt install nginx -y"
  end
end
