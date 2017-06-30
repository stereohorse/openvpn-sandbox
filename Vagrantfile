Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"

  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.manage_guest = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true

  config.vm.define 'vm-vpn' do |node|
    node.vm.hostname = 'vm-vpn'
    node.vm.network :private_network, ip: '192.168.5.2'

    node.vm.provider :virtualbox do |v|
      v.memory = 4096
      v.cpus = 4
    end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "play-site.yml"
  end
end
