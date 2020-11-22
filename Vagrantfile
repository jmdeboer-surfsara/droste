# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
  config.ssh.insert_key = false
  config.vm.box = "minimal/centos7"
  config.vm.box_version = "7.0"
  config.vm.define "droste"
  config.vm.provider "virtualbox" do |vb|
    vb.name = "droste"
    vb.memory = 2048
    vb.customize ["modifyvm", :id, "--ioapic", "on"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
    vb.customize ["modifyvm", :id, "--usb", "off"]
    vb.customize ["modifyvm", :id, "--usbehci", "off"]
  end
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "droste.yml"
  end
end
