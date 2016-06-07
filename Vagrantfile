# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "tests/test.yml"
    ansible.raw_arguments  = [
       "--sudo"
    ]
  end

  config.vm.network "forwarded_port", guest: 5601, host: 15601

end
