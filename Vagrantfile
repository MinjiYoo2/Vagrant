Vagrant.configure("2") do |config|
  config.vm.define:"node1" do |cfg|
    cfg.vm.box = "ubuntu/bionic64"
    cfg.vm.provider:virtualbox do |vb|
        vb.name="node1"
        vb.customize ["modifyvm", :id, "--cpus", 2]
        vb.customize ["modifyvm", :id, "--memory", 2048]
    end
    cfg.vm.host_name="node1"
    cfg.vm.synced_folder ".", "/vagrant", disabled: false
    #cfg.vm.network "public_network", ip: "192.168.56.11"
    cfg.vm.network "private_network", ip: "192.168.56.11", bridge: "en0: Wi-Fi (AirPort)"
    cfg.vm.network "forwarded_port", guest: 22, host: 19211, auto_correct: false, id: "ssh"
    cfg.vm.network "forwarded_port", guest: 80, host: 10080
  end

  config.vm.define:"node2" do |cfg|
    cfg.vm.box = "ubuntu/bionic64"
    cfg.vm.provider:virtualbox do |vb|
        vb.name="node2"
        vb.customize ["modifyvm", :id, "--cpus", 2]
        vb.customize ["modifyvm", :id, "--memory", 2048]
    end
    cfg.vm.host_name="node2"
    cfg.vm.synced_folder ".", "/vagrant", disabled: false
  #  cfg.vm.network "public_network", ip: "192.168.56.12"
    cfg.vm.network "private_network", ip: "192.168.56.12", bridge: "en0: Wi-Fi (AirPort)"
    cfg.vm.network "forwarded_port", guest: 22, host: 19212, auto_correct: false, id: "ssh"
    cfg.vm.network "forwarded_port", guest: 80, host: 20080
  end

  config.vm.define:"master" do |cfg|
    cfg.vm.box = "ubuntu/bionic64"
    cfg.vm.provider:virtualbox do |vb|
        vb.name="master"
        vb.customize ["modifyvm", :id, "--cpus", 4]
        vb.customize ["modifyvm", :id, "--memory", 4096]
    end
    cfg.vm.host_name="master"
    cfg.vm.synced_folder ".", "/vagrant", disabled: false
  #  cfg.vm.network "public_network", ip: "192.168.56.10"
    cfg.vm.network "private_network", ip: "192.168.56.10", bridge: "en0: Wi-Fi (AirPort)"
    cfg.vm.network "forwarded_port", guest: 22, host: 19210, auto_correct: false, id: "ssh"
    cfg.vm.network "forwarded_port", guest: 80, host: 30080
  end
end