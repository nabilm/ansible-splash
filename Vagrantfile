# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  if Vagrant.has_plugin?("vagrant-cachier")
      config.cache.scope = :box
      config.cache.enable :apt
      # We need to have a look if pip caching is now supported in vagrant-cachier
      #config.cache.enable :pip
  end

  config.vm.box = "ubuntu/trusty64"

  config.vm.box_check_update = false

  # Forward the dev server port
  #config.vm.network "forwarded_port", guest: 8000, host: 8080
  config.vm.network "forwarded_port", guest: 8050, host: 7000

  config.vm.network :private_network, ip: "192.168.33.30"

  config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
  end

  config.vm.synced_folder ".", "/vagrant", disabled: true

  # Ansible provisioning
  config.vm.provision "ansible" do |ansible |
      # Local config
      ansible.playbook = "splash_play.yml"
      ansible.verbose = 'vvvv'
      ansible.raw_arguments = ["-e create_swap_file=true"]
  end

end
