
Vagrant.configure("2") do |config|

  config.vm.define "server" do |webserver|

    webserver.vm.box = "ubuntu/trusty64"

    webserver.vm.box_check_update = false

    webserver.vm.network "forwarded_port", guest: 8080, host: 8082

    webserver.vm.network "private_network", type: "static", ip: "192.168.0.10"

    webserver.vm.synced_folder "./tomcatwebapps","/opt/tomcat/webapps"

    webserver.vm.provider "virtualbox" do |vb|
      vb.gui=false
      vb.name="webserver-tomcat"
      vb.memory="1024" 
    end
  end

  config.vm.define "prepodserver" do |prepodwebserver|

    prepodwebserver.vm.box = "bento/ubuntu-22.04"

    prepodwebserver.vm.box_check_update = false

    prepodwebserver.vm.network "forwarded_port", guest: 8080, host: 8083

    prepodwebserver.vm.network "private_network", type: "static", ip: "192.168.0.11"

    prepodwebserver.vm.synced_folder "./tomcatwebapps","/opt/tomcat/webapps"

    prepodwebserver.vm.provider "virtualbox" do |vb|
      vb.gui=false
      vb.name="prepodwebserver"
      vb.memory="1024" 
    end
  end
end
