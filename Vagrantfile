# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "fedora/25-cloud-base"
#  config.vm.synced_folder "userdata", "/home/vagrant/data", type: "sshfs"

  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true
  config.hostmanager.include_offline = true

  (1..3).each do |i|
    config.vm.define "mgmt#{i}" do |node|
      node.vm.hostname = "mgmt#{i}.belbob.thuis"
      node.hostmanager.aliases = "mgmt#{i}"
      node.vm.provider :libvirt do |domain|
          domain.memory = 2048
          domain.cpus = 1
          domain.nested = true
          domain.volume_cache = 'none'
      end
      config.vm.provision "ansible" do |ansible|
          ansible.playbook = "require_python2.yml"
      end
      node.vm.provision :ansible do |ansible|
          ansible.playbook = "required_stuff.yml"
      end
    end
  end

  config.vm.provision :hostmanager

end
