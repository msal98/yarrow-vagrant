# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	config.vm.box = "trusty-x64-server/4.3.24"
	config.vm.box_url = "http://cd1:81/artifactory/vm-artifacts/vagrant/ubuntu/trusty-x64/4.3.24/trusty-x64-server.box"
	config.vm.post_up_message = "Login credentials are vagrant/vagrant"

	# configure defaults - leaving in case other VMs are added
	config.vm.provider "virtualbox" do |v|
		v.gui = false
		v.customize ["modifyvm", :id, "--groups", "/yarrow"]
		v.customize ["modifyvm", :id, "--memory", "256"]
		v.customize ["modifyvm", :id, "--cpus", "1"]
		v.customize ["modifyvm", :id, "--audio", "none"]
		v.customize ["modifyvm", :id, "--clipboard", "bidirectional"]
		v.customize ["modifyvm", :id, "--usb", "off"]
		v.customize ["modifyvm", :id, "--vram", "10"]
	end

	# TODO: Run ansible playbook to provision
	
	config.vm.define "desktop" do |desktop|
		desktop.vm.box = "trusty-x64-desktop/4.3.24"
        desktop.vm.box_url = "http://cd1:81/artifactory/vm-artifacts/vagrant/ubuntu/trusty-x64/4.3.24/trusty-x64-desktop.box"
        desktop.vm.hostname = "desktop"
        desktop.vm.network :private_network, ip: "192.168.99.10"
        desktop.vm.provider "virtualbox" do |v|
            v.gui = true
			# Careful, this name is global to your vbox install... make sure it is unique.
            v.name = "yarrow.desktop"
            v.customize ["modifyvm", :id, "--memory", "4096"]
            v.customize ["modifyvm", :id, "--vram", "24"]
            v.customize ["modifyvm", :id, "--cpus", "2"]
        end
    end
end
