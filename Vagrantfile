servers=[
  {
    :hostname => "dc1",
    :ip => "192.168.10.10",
    :box => "mynewbox",
    :ram => 2048,
    :cpu => 2
  },
  {
    :hostname => "dc2",
    :ip => "192.168.10.11",
    :box => "mynewbox",
    :ram => 2048,
    :cpu => 2
  },
  {
    :hostname => "dc4",
    :ip => "192.168.10.13",
    :box => "mynewbox",
    :ram => 2048,
    :cpu => 2
  },
  {
    :hostname => "dc3",
    :ip => "192.168.10.12",
    :box => "mynewbox",
    :ram => 2048,
    :cpu => 2
  }
]

Vagrant.configure("2") do |config|
    servers.each do |machine|
        config.vm.define machine[:hostname] do |node|
            node.vm.box = machine[:box]
            node.vm.hostname = machine[:hostname]
            node.vm.network "private_network", ip: machine[:ip]
            node.vm.provider "virtualbox" do |vb|
                vb.customize ["modifyvm", :id, "--memory", machine[:ram]]
            end
        end
    end
end
