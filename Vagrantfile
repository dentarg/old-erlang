# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.network "forwarded_port", guest:  5672, host:  5677, auto_correct: true
  config.vm.network "forwarded_port", guest: 15672, host: 15677, auto_correct: true

  config.ssh.insert_key = false

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
  end

  config.vm.define "u14" do |node|
    node.vm.box = "ubuntu/trusty64"
    node.vm.synced_folder "./.",
                       "/vagrant",
                       disabled: false,
                       SharedFoldersEnableSymlinksCreate: false
  end
end
