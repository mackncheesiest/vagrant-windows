# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "opentable/win-2012r2-standard-amd64-nocm"
  config.vm.guest = :windows
  config.vm.communicator = "winrm"
  config.vm.provider :virtualbox do |v|
    v.memory = 6144 
    v.cpus = 4 
    v.customize ["modifyvm", :id, "--accelerate3d", "on", "--accelerate2dvideo", "on", "--vram", "256"]
  end
  config.vm.synced_folder "~/Documents/VBoxSharedFolder", "/shares/VBoxSharedFolder"

  config.vm.provision "shell" do |s|
    s.privileged = true
    s.path = "shell/install_chocolatey.ps1"
  end
  config.vm.provision "shell" do |s|
    s.privileged = true
    s.path = "shell/setup.ps1"
  end
  config.vm.provision "shell" do |s|
    s.privileged = true
    s.path = "shell/final_setup.ps1"
  end
end
