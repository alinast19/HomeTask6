ENV["VAGRANT_EXPERIMENTAL"] = "disks"

Vagrant.configure("2") do |config|
    config.vm.define "hw6" do |hw6|

    hw6.vm.hostname = "hw6"
    hw6.vm.box = "ubuntu/focal64"
    hw6.vm.network "private_network", ip: "192.168.56.8"
    hw6.vm.network "forwarded_port", guest: 80, host: 8888

    for idx in 1..4
      config.vm.disk :disk, size: "300MB", name: "HDD#{idx}"
    end

    hw6.vm.provider "virtualbox" do |vb|
      vb.name = "hw6"
      vb.gui = false
      vb.memory = "1024"
    end

    config.vm.provision "shell", run: "always", path: "script.sh"
  end
end