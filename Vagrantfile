# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_check_update = false
  config.vm.hostname = "ubuntu1604"
  config.vm.define "ubuntu1604"
  config.vm.provider :virtualbox do |vb|
    vb.name = "ubuntu1604"
    vb.gui = false
    vb.memory = "1024"
  end
  config.vm.network :private_network, ip: "192.168.100.100"

  config.ssh.insert_key = false
  config.ssh.private_key_path = ['~/.vagrant.d/insecure_private_key', '~/.ssh/localvagrant_rsa']
  config.vm.provision "file", source: "~/.ssh/localvagrant_rsa.pub", destination: "/home/vagrant/.ssh/authorized_keys"
  config.vm.provision "shell" do |s|
    s.inline = "cp /home/vagrant/.ssh/authorized_keys /root/.ssh/authorized_keys"
    s.privileged = true
  end

end
