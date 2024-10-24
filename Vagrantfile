# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

  config.vm.box = "debian/bookworm64"

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y bind9
  SHELL

  config.vm.define "venus" do |venus| # Esclavo
    venus.vm.network "private_network", ip: "192.168.57.102"
    venus.vm.provision "shell", inline: <<-SHELL
      sudo cp -v /vagrant/files/named /etc/default/
      sudo cp -v /vagrant/files/named.conf.options /etc/bind
      sudo cp -v /vagrant/files/SLAVEnamed.conf.local /etc/bind/named.conf.local
      sudo systemctl restart bind9
    SHELL
  end

  config.vm.define "tierra" do |tierra| # Maestro
    tierra.vm.network "private_network", ip: "192.168.57.103"
    tierra.vm.provision "shell", inline: <<-SHELL
      sudo cp -v /vagrant/files/named /etc/default/
      sudo cp -v /vagrant/files/named.conf.options /etc/bind
      sudo cp -v /vagrant/files/MASTERnamed.conf.local /etc/bind/named.conf.local
      sudo cp -v /vagrant/files/MASTER.sistema.test.dns /var/lib/bind/MASTER.sistema.test.dns
      sudo cp -v /vagrant/files/MASTERsistemaInverso.test.dns /var/lib/bind/MASTERsistemaInverso.test.dns
      echo "nameserver 192.168.57.103" | sudo tee /etc/resolv.conf
      sudo systemctl restart bind9
    SHELL
  end

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Share an additional folder to the guest VM.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Disable the default share of the current code directory.
  # config.vm.synced_folder ".", "/vagrant", disabled: true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant.
  # Example for VirtualBox:
  # config.vm.provider "virtualbox" do |vb|
  #   vb.gui = true
  #   vb.memory = "1024"
  # end
end
