Vagrant.configure("2") do |config|
  nodes = {
    "debian1" => { hostname: "debian1", vmname: "DebianBookwormVM1" },
    "debian2" => { hostname: "debian2", vmname: "DebianBookwormVM2" }
  }

  nodes.each do |name, opts|
    config.vm.define name do |node|
      node.vm.box = "debian/bookworm64"
      node.vm.hostname = opts[:hostname]

      node.vm.provider "virtualbox" do |vb|
        vb.name = opts[:vmname]
        vb.cpus = 2
        vb.memory = 1024
      end

      node.vm.network "private_network", type: "dhcp"
    end
  end
end
