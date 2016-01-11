Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  #config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "public_network",
      use_dhcp_assigned_default_route: true,
      bridge: "enp1s0"
  
  config.vm.synced_folder "www/", "/var/www/html",
	owner: "vagrant", group: "www-data"

  config.vm.provision :ansible do |ansible|
	ansible.playbook = "playbook.yml"
  end
end
