# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure(2) do |config|
  
  config.vm.box = "centos-6.5"

 config.vm.provision "file", source: "C:\\Users\\projects\\demo\\files\\git-config", destination: "~/.gitconfig"
 
 
  # config.vm.box_check_update = false

  
  config.vm.network "forwarded_port", guest: 8080, host: 8080

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

 
   config.vm.provider "virtualbox" do |vb|
  
     vb.memory = "1024"
   end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

 config.vm.provision "chef_solo" do |chef|
  chef.cookbooks_path = "C:\\Users\\projects\\tomcat-chef\\supermarket"
  chef.add_recipe "java"
  chef.json = {
  "java" => {
     "jdk_version" => "7"
   }
  }
 end

end
