# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # VirtualBox
  config.vm.box = "ubuntu/xenial64"

  # Enable the bootstrap-script
  config.vm.provision :shell, :path => "bootstrap.sh"

  config.vm.network "forwarded_port", guest: 80, host: 8080
  config.vm.network "forwarded_port", guest: 8000, host: 8000

  config.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777", "fmode=666"]

  config.push.define "heroku" do |push|
    push.app = "vaalikilke"
  end
end


