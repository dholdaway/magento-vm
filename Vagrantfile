# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  #config.vm.host_name = "foo"
  config.vm.box = "centos65-x86_64-20140116"
  config.vm.box_url = "https://github.com/2creatives/vagrant-centos/releases/download/v6.5.3/centos65-x86_64-20140116.box"

  config.vm.forward_port 80, 8080

  config.vm.share_folder "v-data", "/vagrant_data", "data"

  config.vm.provision :shell, :inline => "sudo yum update && sudo yum install puppet -y"

  config.vm.provision :puppet do |puppet|
     puppet.manifests_path = "puppet/manifests"
     puppet.manifest_file  = "base.pp"
     puppet.module_path    = "puppet/modules"
     #puppet.options        = "--verbose --debug"
  end
end
