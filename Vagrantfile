VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "trusty64"
  config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.network :private_network, ip: "192.168.50.51"

  config.vm.hostname = 'help.local'

  config.vm.synced_folder '.', '/vagrant', nfs: true

  config.vm.provider "virtualbox" do |v|
    v.memory = 1024
  end

  config.vm.provision :ansible do |ansible|
    ansible.limit = 'all'
    ansible.playbook = "vm/vagrant.yml"
    ansible.inventory_path = "vm/vagrant"
  end
end
