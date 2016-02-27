# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.ssh.forward_agent = true
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/site.yml"
    ansible.groups = {
      "dev" => ["default"]
    }
    ansible.extra_vars = {
      project_path: "/vagrant",
      processor_architecture: "x64"
    }
  end


  config.vm.provider "virtualbox" do |v, override|
    v.memory = 2048
    v.cpus = 2
    override.vm.network "private_network", ip: "192.168.33.17"
  end

  config.vm.provider "lxc" do |v, override|
    override.vm.box = "fgrehm/trusty64-lxc"
    override.vm.network :forwarded_port, host: 5000, guest: 80
  end
end
