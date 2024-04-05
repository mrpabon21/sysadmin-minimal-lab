Vagrant.configure(2) do |config|

    config.vm.define "webapp1" do |webapp1|
        webapp1.vm.box = "ubuntu/jammy64"
        webapp1.vm.provider "virtualbox" do |v|
            v.memory = 1024
            v.cpus = 1
        end
        webapp1.vm.hostname = "webapp1"
        webapp1.vm.network "private_network", ip: "192.168.56.10"

        webapp1.vm.provision "ansible" do |ansible|
            ansible.playbook = "playbooks/webapp1.yml"
        end
    end
  
    config.vm.define "db1" do |db1|
        db1.vm.box = "ubuntu/jammy64"
        db1.vm.provider "virtualbox" do |v|
            v.memory = 1024
           v.cpus = 1
        end
        db1.vm.hostname = "db1"
        db1.vm.network "private_network", ip: "192.168.56.11"
        db1.vm.provision "ansible" do |ansible|
          ansible.playbook = "playbooks/db1.yml"
        end
    end

end
