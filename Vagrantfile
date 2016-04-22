# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "debian", autostart: false do |debian|
	  debian.vm.box = "debian/jessie64"
	  debian.vm.provision :shell, path: "vagrant/provision.sh"
	  debian.vm.hostname = "ownsocial2-debian"
	  debian.vm.network "private_network", ip: "192.168.35.30"
	  debian.hostsupdater.aliases = ["debian.ownsocial2.local"]
	  debian.vm.synced_folder ".", "/vagrant", {:owner => "www-data", :group => "www-data"}
  end

  config.vm.define "ubuntu", primary: true do |ubuntu|
  	  ubuntu.vm.box = "ubuntu/trusty64"
  	  ubuntu.vm.provision :shell, path: "vagrant/provision.sh"
  	  ubuntu.vm.hostname = "ownsocial2-ubuntu"
  	  ubuntu.vm.network "private_network", ip: "192.168.35.40"
  	  ubuntu.hostsupdater.aliases = ["ownsocial2.local", "ubuntu.ownsocial2.local"]
  	  ubuntu.vm.synced_folder ".", "/vagrant", {:owner => "www-data", :group => "www-data"}
    end

end
