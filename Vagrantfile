# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define "lb1" do |lb1|
    lb1.vm.box = "ubuntu/bionic64"
    lb1.vm.network "private_network", ip: "192.168.56.10"
    lb1.vm.provision "shell", path: "https://gist.githubusercontent.com/geraldGhibran/6a000c7f6f696abadcf57878d165877b/raw/d1b3662117ffc58ac6ba7f2193eff1f807838f39/load-balancer1.sh"
  end

  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/bionic64"
    web1.vm.network "private_network", ip: "192.168.56.11"
    web1.vm.provision :shell do |shell|
      shell.args = "1"
      shell.path = "https://gist.githubusercontent.com/geraldGhibran/520cab16b9343d2ccd041f4ddb6ad62e/raw/7dee35ab1707847fd23c205ec8bc2eabc546b258/provision-web.sh"
    end
  end

  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/bionic64"
    web2.vm.network "private_network", ip: "192.168.56.12"
    web2.vm.provision :shell do |shell|
      shell.args = "2"
      shell.path = "https://gist.githubusercontent.com/geraldGhibran/520cab16b9343d2ccd041f4ddb6ad62e/raw/7dee35ab1707847fd23c205ec8bc2eabc546b258/provision-web.sh"
    end
  end

  config.vm.define "dbMain" do |dbMain|
    dbMain.vm.box = "ubuntu/bionic64"
    dbMain.vm.network "private_network", ip: "192.168.56.200"
    dbMain.vm.provision :shell do |shell|
      shell.args = "3"
      shell.path = "https://gist.githubusercontent.com/geraldGhibran/394838884312d3a87d8937f7ee8dd7bf/raw/14b96a5c45df0b185f7a50aa19c0475529cb6bb1/db-main.sh"
    end
  end
end
