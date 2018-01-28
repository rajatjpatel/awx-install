ENV['VAGRANT_DEFAULT_PROVIDER'] = 'libvirt'
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.provider "libvirt" do |libvirt|
    config.vm.box = "centos/7"
    libvirt.driver = "kvm"
    libvirt.memory = 2048
    libvirt.cpus = 2
  end
  config.vm.network "forwarded_port", guest: 80, host: 7252
config.vm.provision :ansible do |ansible|
ansible.playbook = "awx.yml"
end
end