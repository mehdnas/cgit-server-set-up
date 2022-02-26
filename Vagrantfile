# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "debian/bullseye64"

  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  # I use Qemu as a provider so if you use it as well, you have to install
  # libvirt pluging for Vagrant (vagrant plugin install vagrant-libvirt).
  # If you want to use virtual box (or another provider), you have to
  # change this part.
  config.vm.provider :libvirt do |v|
    v.memory = 1024
    v.qemu_use_session = false
    v.storage :file, :size => '4G', :bus => 'usb', :device => 'sda'
  end

  config.vm.define "testServer" do |ts|
    ts.vm.hostname = "raspberrypi.test"
    ts.vm.network :private_network, ip: "192.168.2.11"
  end

end
