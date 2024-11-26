Vagrant.configure("2") do |config|
  # VM CONFIGURATION
  config.vm.define :vm01 do |vm01|
    vm01.vm.box = "almalinux/9"
  #config.vm.box_version = "3.0.0"
    vm01.vm.network "private_network", ip: "192.168.50.100"
    vm01.vm.hostname = "vm01"
    #vm01.vm.synced_folder ".", "/vagrant", disabled: true
    #vm01.vm.boot_timeout = 600

  # VM RESOURCE CONFIGURATION
    vm01.vm.provider "vmware_fusion" do |vmf|
      vmf.memory = 1024
      vmf.cpus = 1
    end 
    # ANSIBLE CONFIGURATION
    vm01.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible_playbook.yml"
      #ansible.verbose = "vvv"
    end
  end
end