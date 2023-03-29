# -*- mode: ruby -*-
# vi: set ft=ruby  :

NODES = 2
IMAGE_NAME = "bento/ubuntu-16.04"

# Memory
MASTER_MEMORY=2048
NODE_MEMORY=1024

# Network
NETWORK_PREFIX="192.168.165"
MASTER_IP_ADDRESS="192.168.165.117"

Vagrant.configure("2") do |config|

#   config.ssh.insert_key = false

    config.vm.define "docker-master" do |master|
        master.vm.box = IMAGE_NAME
        master.vm.network "private_network", ip: MASTER_IP_ADDRESS
        master.vm.hostname = "docker-master"
        master.vm.provider :virtualbox do |vb|
            vb.name = "docker-master"
            vb.memory = MASTER_MEMORY
            vb.cpus = 2
            vb.customize ["modifyvm", :id, "--groups", "/bonde-cka"]
        end
    end

    # (1..NODES).each do |i|
    #     config.vm.define "docker-node-#{i}" do |node|
    #         node.vm.box = IMAGE_NAME
    #         node.vm.network "private_network", ip: "#{NETWORK_PREFIX}.#{i + 10}"
    #         node.vm.hostname = "node-#{i}"
    #         node.vm.provider :virtualbox do |vb|
    #             vb.name = "docker-node-#{i}"
    #             vb.memory = NODE_MEMORY
    #             vb.cpus = 2
    #             vb.customize ["modifyvm", :id, "--groups", "/bonde-cka"]
    #         end
    #     end
    # end
    #     config.vm.provision "ansible" do |ansible|
    #         ansible.playbook = "docker-setup/playbook.yml"
    #         ansible.limit = "all"
    #         ansible.extra_vars = {
    #             MASTER_IP_ADDRESS: MASTER_IP_ADDRESS,
    #         }
    #         ansible.groups = {
    #         "nodes" => ["docker-node-[1:2]"],
    #         "docker-master" => ["docker-master"],
    #         }
    # end
end