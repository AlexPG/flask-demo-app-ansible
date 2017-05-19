hosts = {
  "flask-demo-app" => "192.168.33.14"
}

Vagrant.configure("2") do |config|
  hosts.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "ubuntu/trusty64"
      machine.vm.hostname = "demo-app"
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.customize ["modifyvm", :id, "--memory", 200]
      end
    end
  end
end