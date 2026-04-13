Vagrant.configure("2") do |config|                              # Use Vagrant version 2 configuration
  config.vm.box = "ubuntu/jammy64"                              # Define the base image (box)

  # --- Global VM Hardware Settings --- #
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1048                                            # Memory in MB
    vb.cpus = 1                                                 # CPU cores
  end

  # --- VM 1: Ansible Control Node --- #
  config.vm.define "ansible" do |ctrl|
    ctrl.vm.hostname = "ansible-ctrl"
    ctrl.vm.network "private_network", ip: "192.168.99.10"      # Add a static, private IP

    # Automation: Provisioning scripts
    ctrl.vm.provision "shell", inline: <<-SHELL
      apt-get update                                            # Update packages
      apt-get install -y ansible                                # Start Apache
      echo "=== Ansible Initialized ==="
    SHELL
  end

end