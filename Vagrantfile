Vagrant.configure("2") do |config|
# Jenkins
  config.vm.define "vm1" do |vm1|
    vm1.vm.box = "generic/centos8"
    vm1.vm.network "public_network", bridge: "wlo1", ip: "192.168.1.203"
    vm1.vm.hostname = "vm1"
    vm1.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
    vm1.vm.provision "shell", inline: <<-SHELL
      sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
      sudo systemctl restart sshd
    SHELL
  end
 
  config.vm.define "vm2" do |vm2|
    vm2.vm.box = "generic/centos8"
    vm2.vm.network "public_network", bridge: "wlo1", ip: "192.168.1.204"
    vm2.vm.hostname = "vm2"
    vm2.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
    end
    vm2.vm.provision "shell", inline: <<-SHELL
      sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config
      sudo systemctl restart sshd
    SHELL
  end
end	
