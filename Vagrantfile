# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  config.vm.define :el6 do |el6|
      el6.vm.box = "centos/6"
      el6.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_rhel.yml"
    end
  end

  config.vm.define :el7 do |el7|
    el7.vm.box = "centos/7"
    el7.vm.provision :ansible do |ansible|  
      ansible.playbook = "compile_mydumper_rhel.yml"
    end
  end

  config.vm.define :debian9 do |debian9|
    debian9.vm.box = "debian/stretch64"
    debian9.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  config.vm.define :debian8 do |debian8|
    debian8.vm.box = "debian/jessie64"
    #debian8.vm.box_url = "https://github.com/kraksoft/vagrant-box-debian/releases/download/8.1.0/debian-8.1.0-amd64.box"
    debian8.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  config.vm.define :debian7 do |debian7|
    debian7.vm.box = "debian/wheezy64"
    #debian7.vm.box_url = "https://github.com/kraksoft/vagrant-box-debian/releases/download/7.8.0/debian-7.8.0-amd64.box"
    debian7.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  config.vm.define :trusty do |trusty|
    trusty.vm.box = "ubuntu/trusty64"
    trusty.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  config.vm.define :xenial do |xenial|
    xenial.vm.box = "ubuntu/xenial64"
    xenial.vm.provision "install pyhton 2.7",
      type: "shell",
      preserve_order: true,
      inline: "apt-get -y install python"
    xenial.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  config.vm.synced_folder '.', '/vagrant', disabled: true

end
