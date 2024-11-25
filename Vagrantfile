 Vagrant.configure("2") do |config|
  # VM CONFIGURATION
  config.vm.box = "almalinux/9"
  #config.vm.box_version = "3.0.0"
  config.vm.network "private_network", ip: "192.168.50.100"
  config.vm.hostname = "vm01"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.boot_timeout = 600

  # VM RESOURCE CONFIGURATION
  config.vm.provider "vmware_fusion" do |vmf|
    vmf.memory = 1024
    vmf.cpus = 1
    # ANSIBLE CONFIGURATION
    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible_playbook.yml"
      ansible.verbose = "vvv"
      #ansible.become = true
      #ansible.become_user = "root"
    end
  end
end