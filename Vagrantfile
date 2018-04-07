# This file will be used by "vagrant up" to load debian 8 (aka "Jessie")
# and run ansible with playbook

# Define local name + IP address
BOX_NAME="joomlabox.test"

# Check in VirtualBox: File > Host Network Manager, and take IP within that range
DEFAULT_IP="192.168.33.100"

require "resolv"

def my_ip
  @my_ip ||= Resolv::Hosts.new.getaddress(BOX_NAME) || DEFAULT_IP
rescue
  @my_ip ||= DEFAULT_IP
end

Vagrant.configure(2) do |config|

  config.ssh.forward_agent = true

  config.vm.define :joomlabox do |jb|
    jb.vm.box      = "debian/jessie64"
    jb.vm.network  "private_network", ip: my_ip
    #jb.vm.network  "forwarded_port", guest: 80, host: 8080
    jb.vm.hostname = BOX_NAME

    jb.vm.provider "virtualbox" do |vb|
      # Display the VirtualBox GUI when booting the machine
       vb.gui = true

      # Customize the amount of memory on the VM:
      vb.customize ["modifyvm", :id, "--memory", "2048"]
      vb.customize ["modifyvm", :id, "--vram", "18"]
      vb.customize ["modifyvm", :id, "--cpus", "2"]
      vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = 'ansible/site.yml'
    ansible.verbose  = 'v'
  end
end
