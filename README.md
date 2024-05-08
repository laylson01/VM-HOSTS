# Guia de Instalação do Vagrant e VirtualBox

Para começar a usar o Vagrant, você precisa primeiro baixar e instalar o Vagrant e o VirtualBox.

## Passo 1: Baixar o Vagrant

1. Acesse o [site oficial do Vagrant](https://www.vagrantup.com/downloads).
2. Escolha a versão do Vagrant adequada para o seu sistema operacional.
3. Faça o download do instalador.
3. Após o download, execute o instalador do Vagrant.
4. Siga as instruções do assistente de instalação para concluir a instalação.

## Passo 3: Baixar o VirtualBox

1. Acesse o [site oficial do VirtualBox](https://www.virtualbox.org/wiki/Downloads).
2. Escolha a versão do VirtualBox adequada para o seu sistema operacional.
3. Faça o download do instalador.
4. Após o download, execute o instalador do VirtualBox.
5. Siga as instruções do assistente de instalação para concluir a instalação.

Agora que você baixou e instalou o Vagrant e o VirtualBox, você está pronto para começar a criar e gerenciar suas máquinas virtuais com facilidade usando o Vagrant.


# Configuração do Vagrant (Host)

## Método `common_provision_script`
Este método contém um script que será executado em todas as máquinas virtuais para realizar tarefas comuns de configuração, como atualizar pacotes, instalar programas (Nginx, GCC, Make) e limpar o sistema.

## Configuração do Vagrant
Este é o bloco principal onde a configuração das máquinas virtuais é definida.

## Método `configure_machine`
Este método recebe quatro parâmetros (configuração, nome, caixa e endereço IP) e configura uma máquina virtual com esses detalhes. Ele define a caixa (imagem da máquina virtual), a rede privada com um endereço IP especificado e uma pasta sincronizada para compartilhar arquivos entre o host e a máquina virtual.

## Configuração de máquinas virtuais
Aqui, o método `configure_machine` é chamado três vezes para configurar três máquinas virtuais diferentes: host1, host2 e biglinux. Cada chamada especifica o nome da máquina, a caixa a ser usada e o endereço IP da rede privada.

Em resumo, este código cria três máquinas virtuais (host1, host2 e biglinux) e as configura com scripts de provisionamento comum para atualizar pacotes, instalar programas e limpar o sistema.
