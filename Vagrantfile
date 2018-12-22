Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"
  config.vm.hostname = 'BionicDev'
  config.vm.box_check_update = true

  # no port forwarding, but leaving comment for now
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  # config.vm.network "private_network", ip: "192.168.33.10"
  # config.vm.network "public_network"

  # Creating a /project folder that's external from the VM
  config.vm.synced_folder "../Project", "/project"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "BionicDev"
    vb.memory = "4096"
  end

  #run some shell commands to bring this machine up to scratch
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update && apt-get upgrade -y
  #  apt-get install -y 
  SHELL

end
