Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-16.04"

  config.vm.define "target" do |target|
    target.vm.network "private_network", ip: "10.155.0.11"
    target.vm.hostname = "target"
  end

  config.vm.define "jump" do |jump|
    jump.vm.network "forwarded_port", guest: 22, host: 2244
    jump.vm.network "private_network", ip: "10.155.0.10"

    jump.vm.provision "shell", inline: "echo 10.155.0.11 target >> /etc/hosts"
    jump.vm.hostname = "jump"
  end

  config.vm.provision "ansible_local" do |a|
    a.playbook = "playbook.yml"
  end
end
