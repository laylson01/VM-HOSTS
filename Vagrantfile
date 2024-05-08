# Vagrantfile para criar três máquinas virtuais: host1, host2 e host3

# Script de provisionamento a ser executado em todas as máquinas
$common_script = <<-EOF
  sudo apt-get update && sudo apt-get upgrade -y
  sudo apt autoremove -y
  sudo apt install nginx gcc make -y
EOF

# Script de provisionamento para instalar o KDE Plasma (interface gráfica) apenas no host3
$kde_install_script = <<-EOF
  sudo apt update
  sudo apt install kubuntu-desktop -y
EOF


# Configuração do Vagrant
Vagrant.configure("2") do |config|
  # Método para configurar uma máquina
  def configure_machine(config, name, box, ip, provision_script)
    config.vm.define name do |machine|
      machine.vm.box = box
      machine.vm.network "private_network", ip: ip
      config.vm.synced_folder ".", "/vagrant"

      # Provisionamento da máquina
      machine.vm.provision "shell", inline: provision_script
    end
  end

  # Configuração da máquina host1
  configure_machine(config, "host1", "ubuntu/bionic64", "192.168.0.12", $common_script)

  # Configuração da máquina host2
  configure_machine(config, "host2", "debian/buster64", "192.168.0.13", "sudo apt update && sudo apt install nginx -y")

  # Configuração da nova máquina host3 com BigLinux
  configure_machine(config, "host3", "biglinux/biglinux-20.04-amd64", "192.168.0.14", $common_script + $kde_install_script)
end
