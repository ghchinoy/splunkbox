# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "c65"
  # config.vm.box_url = "http://vntx.cc/boxes/centos65.box"

  # Assign a hostname unique to this project.
  config.vm.hostname = "splunk.vagrant"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network :private_network, ip: "10.10.10.5"

  config.vm.network :forwarded_port, guest: 80, host: 8080


  config.vm.provider :virtualbox do |vb|
    vb.gui = false
  end

  # provision with ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook          = "playbook.yaml"
    ansible.sudo              = true
    ansible.host_key_checking = false
    # ansible.extra_vars        = { installapps: false }
  end
end
