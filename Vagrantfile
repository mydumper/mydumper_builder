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
  
  # Debian 9
  config.vm.define :stretch do |stretch|
    stretch.vm.box = "debian/stretch64"
    stretch.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  # Debian 8
  config.vm.define :jessie do |jessie|
    jessie.vm.box = "debian/jessie64"
    #debian8.vm.box_url = "https://github.com/kraksoft/vagrant-box-debian/releases/download/8.1.0/debian-8.1.0-amd64.box"
    jessie.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  # Debian 7
  config.vm.define :wheezy do |wheezy|
    wheezy.vm.box = "debian/wheezy64"
    #debian7.vm.box_url = "https://github.com/kraksoft/vagrant-box-debian/releases/download/7.8.0/debian-7.8.0-amd64.box"
    wheezy.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  # Ubuntu 14
  config.vm.define :trusty do |trusty|
    trusty.vm.box = "ubuntu/trusty64"
    trusty.vm.provision :ansible do |ansible|
      ansible.playbook = "compile_mydumper_debian.yml"
    end
  end

  # Ubuntu 16
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
