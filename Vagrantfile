VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos7"

  config.vm.define "master" do |master|
    master.vm.hostname = "master"
    master.vm.network "forwarded_port", guest: 3306, host: 3336
    master.vm.network "private_network", ip: "192.168.56.101"
  end

  config.vm.define "slave" do |slave|
    slave.vm.hostname = "slave"
    slave.vm.network "forwarded_port", guest: 3306, host: 3337
    slave.vm.network "private_network", ip: "192.168.56.104"
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048
    v.cpus = 2
  end
end
