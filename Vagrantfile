Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.hostname = "otus"
  config.vm.network "public_network", ip: "192.168.1.100"
  config.vm.provider "virtualbox" do |vb|
     vb.gui = false
     vb.memory = "2048"
     vb.cpus = "2"
  config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     sudo apt-get install linux-image-unsigned-5.8.0-28-generic -y
     sudo update-grub
   SHELL

   config.vm.provision "shell", inline: "sudo reboot", run: "always"
  end
end
