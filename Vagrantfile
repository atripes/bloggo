$hostname = "bloggo.local"

Vagrant.configure("2") do |config|

  config.vm.box = "bento/ubuntu-18.04"

  config.vm.define $hostname do |machine|
    machine.vm.hostname = $hostname

    machine.vm.network :private_network, ip: "10.0.0.128"

    machine.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy/playbook.yml"
      ansible.groups = {
          "local" => 'default'
      }
      ansible.extra_vars = {
        target: 'all'
      }
      #ansible.raw_arguments = [
      #  '-vvv'
      #]
    end

    machine.vm.provider "virtualbox" do |vbox|
      vbox.name = $hostname
    end
  end
end
