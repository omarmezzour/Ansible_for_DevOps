# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "logging_server" do |logging_server|
    logging_server.vm.box = "ubuntu/bionic64"
    logging_server.vm.network "private_network", ip: "192.168.56.4"
    logging_server.vm.provision "ansible" do |ansible|
      ansible.playbook = "logging_server/ansible/logging_server_playbook.yml"
    end
  end

  config.vm.define "db_server" do |db_server|
    db_server.vm.box = "ubuntu/bionic64"
    db_server.vm.network "private_network", ip: "192.168.56.5"
    db_server.vm.provision "ansible" do |ansible|
      ansible.playbook = "db_server/ansible/db_server_playbook.yml"
    end
  end

  config.vm.define "web_app_server" do |web_app_server|
    web_app_server.vm.box = "ubuntu/bionic64"
    web_app_server.vm.network "private_network", ip: "192.168.56.6"
    web_app_server.vm.provision "ansible" do |ansible|
      ansible.playbook = "web_app_servers/ansible/web_app_server_playbook.yml"
    end
  end

  # Disable the insecure ssh key
  config.ssh.insert_key = false

  # Customize the amount of memory on the VM
  config.vm.provider "virtualbox" do |v|
    v.memory = "2048"
  end
end
