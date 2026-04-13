Vagrant.configure("2") do |config|                              # Use Vagrant version 2 configuration
  config.vm.box = "ubuntu/jammy64"                              # Define the base image (box)

  # --- Global VM Hardware Settings --- #
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1048                                            # Memory in MB
    vb.cpus = 1                                                 # CPU cores
  end

  # --- VM 1: Node --- #
  config.vm.define "vm-git-test" do |vm|
    vm.vm.hostname = "vm-git-test"
    vm.vm.network "private_network", ip: "192.168.99.10"      # Add a static, private IP

    # Automation: Provisioning scripts
    vm.vm.provision "shell", inline: <<-SHELL
      git clone https://github.com/sanjarbsaraee/git-test.git
    SHELL
  end

end