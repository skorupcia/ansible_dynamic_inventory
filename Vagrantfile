# -*- mode: ruby -*-
# vi: set ft=ruby :                                 

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General Vagrant VM configuration.
  config.vm.box = "luminositylabsllc/bento-ubuntu-20.04-arm64"
  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", type: "rsync",
    rsync__exclude: ".git/"
  config.vm.provider "parallels" do |prl|
    prl.memory = 512
    prl.linked_clone = true
  end
  # Application server 1.
  config.vm.define "inventory1" do |inventory|
    inventory.vm.hostname = "inventory1.test" 
    inventory.vm.network :private_network, ip: "192.168.56.71"
  end
  # Application server 2.
  config.vm.define "inventory2" do |inventory|
    inventory.vm.hostname = "inventory2.test" 
    inventory.vm.network :private_network, ip: "192.168.56.72"
  end
end