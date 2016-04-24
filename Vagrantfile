# Source: http://blog.zenika.com/2014/10/07/setting-up-a-development-environment-using-docker-and-vagrant/

ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'
 
Vagrant.configure("2") do |config|

  config.vm.synced_folder ".", "/usr/local/src"

  config.vm.define "vertxdev-src" do |a|
    a.vm.provider "docker" do |d|
      d.build_dir = "."
      d.build_args = ["-t=vertxdev"]
      d.ports = ["8080:8080"]
      d.name = "vertxdev-src"
      d.remains_running = true
      d.cmd = ["vertx", "run", "vertx-examples/src/raw/java/httphelloworld/HelloWorldServer.java"]
      d.vagrant_machine = "dockerhost"
      d.vagrant_vagrantfile = "./VagrantfileDockerHost"
    end
  end

end