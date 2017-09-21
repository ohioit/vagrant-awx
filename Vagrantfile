# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provider :virtualbox do |vb|
    vb.memory = 2048
    vb.cpus = 2
  end

  config.vm.define "awx" do |awx|
    awx.vm.hostname = "awx"
    awx.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.config_file = "ansible.cfg"
      ansible.become = true
    end
  end

end
