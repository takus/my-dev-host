# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "opscode-centos-6.4"

  config.vm.define :general do |c|
    c.vm.hostname = 'my-dev-host'
    c.vm.network :private_network, ip: "192.168.33.100"

    c.vm.provider 'virtualbox' do |v|
      v.customize [ 'modifyvm', :id, '--memory', 1024, '--cpus', 4 ]
    end

    config.omnibus.chef_version = "11.4.0"

    c.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = [ 'cookbooks', 'site-cookbooks', 'vendor/cookbooks' ]
      chef.roles_path     = [ 'roles' ]
      chef.data_bags_path = [ 'data_bags' ]
      chef.add_recipe 'yum::epel'
      chef.add_recipe 'git'
      chef.add_recipe 'vim'
      chef.add_recipe 'tmux'
    end
  end

end
