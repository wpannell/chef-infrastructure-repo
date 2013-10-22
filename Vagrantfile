# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "windows_server_2012_vmware"
  config.vm.guest = :windows  

  config.vm.network :forwarded_port, guest: 80, host: 8080

  config.vm.network :private_network, ip: "192.168.33.10"

  # config.vm.network :public_network
  # config.ssh.forward_agent = true

  config.vm.provision :chef_client do |chef|
    chef.chef_server_url = "https://api.opscode.com/organizations/ventana"
    chef.validation_key_path = "wpannell.pem"
    chef.validation_client_name = "ventana-validator"
  end
end
