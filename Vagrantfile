# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_SERVER_URL'] = 'https://vagrant.elab.pro'
Vagrant.configure("2") do |config|
    # Base VM OS configuration.
    config.vm.box = "bento/ubuntu-24.04"
    config.vm.provider :virtualbox do |v|
      v.memory = 1512
      v.cpus = 2
    end
  
    # Define two VMs with static private IP addresses.
    boxes = [
      { :name => "elk",
        :ip => "192.168.56.160",
      },
      { :name => "clientnginx",
        :ip => "192.168.56.150",
      }
    ]
    # Provision each of the VMs.
    boxes.each do |opts|
      config.vm.define opts[:name] do |config|
        config.vm.hostname = opts[:name]
        config.vm.network "private_network", ip: opts[:ip]
  
      end
    end
  end