nodes = [
  { :hostname => "master1", :ip => "10.0.0.10"},
  { :hostname => "worker1", :ip => "10.0.0.12"},
  { :hostname => "worker2", :ip => "10.0.0.13"},
]

Vagrant.configure("2") do |config|

  nodes.each do |node|
    config.vm.define node[:hostname] do |conf|
      conf.vm.box = "hashicorp/bionic64"
      #Uncomment this line to disable the vagrant shared folder
      #conf.vm.synced_folder '.', '/vagrant', disabled: true
      conf.vm.hostname = node[:hostname]
      conf.vm.network :private_network, ip: node[:ip]
    end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = false
    ansible.limit = "all"
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "provisioning/playbook.yml"
  end
end
