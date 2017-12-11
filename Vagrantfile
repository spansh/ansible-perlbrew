# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|

  # Ensure we use our vagrant private key
  config.ssh.insert_key = false
  config.ssh.private_key_path = '~/.vagrant.d/insecure_private_key'

#  config.vm.define 'ubuntu-vm' do |machine|
#    machine.vm.box = "bento/ubuntu-16.04"
#
#    machine.vm.network :private_network, ip: '192.168.88.22'
#    machine.vm.hostname = 'ubuntu-vm'
#
#    machine.vm.provision 'ansible' do |ansible|
#      ansible.verbose = 'v'
#      ansible.playbook = 'tests/playbook.yml'
#      ansible.sudo = true
#      ansible.inventory_path = 'vagrant-inventory'
#      ansible.host_key_checking = false
#    end
#
#  end

  config.vm.define 'centos-vm' do |machine|
    machine.vm.box = "bento/centos-7.4"

    machine.vm.network :private_network, ip: '192.168.88.33'

    # machine.vm.network "forwarded_port", guest: 22,  host: 11222, id: 'ssh'
    machine.vm.hostname = 'centos-vm'

    machine.vm.provision 'ansible' do |ansible|
      #ansible.verbose = 'v'
      ansible.playbook = 'tests/playbook.yml'
      ansible.sudo = true
      ansible.inventory_path = 'vagrant-inventory'
      ansible.host_key_checking = false
    end

  end
end
