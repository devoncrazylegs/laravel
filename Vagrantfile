Vagrant.configure("2") do |config|

    # Set Vagrant box to use
    config.vm.box = "ubuntu/trusty64"

    # Configure port forwarding
    config.vm.network :forwarded_port, guest: 80, host: 8931, auto_correct: true

    # Set synched folder
    config.vm.synced_folder "./", "/var/www", create: true, group: "www-data", owner: "www-data"

    # Configure the VM
    config.vm.provider "virtualbox" do |v|
        v.name = "Jim's test Laravel box"
        v.customize ["modifyvm", :id, "--memory", "1024"]
    end

    # Set up shell provisioning
    config.vm.provision :shell, :path => "bootstrap.sh"
end