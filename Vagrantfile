# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box      = "wordpress"

  config.vm.box_url  = "http://cloud-images.ubuntu.com/precise/current/precise-server-cloudimg-vagrant-amd64-disk1.box"
  config.vm.hostname = "wordpress"

  config.vm.network  :private_network, ip: "192.168.254.254"

  config.vm.provider :virtualbox do |vb|
    vb.gui = true || false
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = 'site.yml'
    ansible.sudo     = true
  end
end
