Vagrant.configure("2") do |config|
  (1..2).each do |i|
    config.vm.define "debian#{i}" do |node|
      node.vm.box = "debian/bookworm64"
      node.vm.hostname = "debian#{i}"

      node.vm.provider "virtualbox" do |vb|
        vb.name = "DebianBookwormVM#{i}"
        vb.cpus = 2
        vb.memory = 1024
      end

      node.vm.network "private_network", type: "dhcp"
    end
  end
end