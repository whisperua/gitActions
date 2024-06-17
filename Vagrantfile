# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Use the ubuntu/jammy64 box
  config.vm.box = "ubuntu/jammy64"

  # Configure private networking with IP 192.168.100.100
  #config.vm.network "private_network", ip: "192.168.100.100"

  # Configure Virtualbox with at least 2 CPUs and 4096 MB Memory
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
    vb.cpus = 2
  end
  # config.vm.synced_folder "../data", "/vagrant_data"
  config.vm.synced_folder "../GitActions", "/vagrant"

  # Inline shell script to install openjdk-17-jdk package
  install_deps = <<~SCRIPT
    sudo apt update
  SCRIPT

  # Run the shell script using shell provisioner
  #config.vm.provision "shell", inline: install_deps

  # Configure a Vagrant trigger to execute after vagrant up
  #config.trigger.after :up do |trigger|
  #  trigger.run_remote = { inline: "cd /vagrant && ./gradlew bootRun" }
  #end
end
