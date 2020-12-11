# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.network :public_network,
      :dev => "virbr0",
      :mode => "bridge",
      :type => "bridge"
  config.vm.synced_folder ".", "/vagrant_data", disabled: true
  config.vm.provider :libvirt do |libvirt|
    libvirt.cpus = 2
    libvirt.memory = 4096
    libvirt.nested = true
  end
  config.vm.provision "ansible" do |a|
    a.verbose = "v"
    a.playbook = "playbook.yaml"
  end
end
