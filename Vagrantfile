
Vagrant.configure(2) do |config|

    config.vm.box = "ubuntu/trusty64"
    
    config.vm.network :private_network, ip: "192.168.80.82"
    config.vm.network "forwarded_port", guest: 80, host: 8082

    config.vm.hostname = "parkrunsearch"

    config.vm.synced_folder "html/", "/var/www/html",
    owner: "root", group: "root"

    config.vm.provision :ansible do |ansible|
        ansible.playbook = "playbook.yml"
    end

    config.vm.provider :virtualbox do |vb|
        vb.name = "parkrunsearch"
    end

end
