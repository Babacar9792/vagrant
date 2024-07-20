
Vagrant.configure("2") do |config|

  config.vm.define "server" do |webserver|

    webserver.vm.box = "ubuntu/trusty64"

    webserver.vm.box_version = "20191107.0.0"

    webserver.vm.box_check_update = false

    webserver.vm.network "forwarded_port", guest: 8080, host: 8082

    webserver .vm.network "private_network", type: "static", ip: "192.168.33.10"

    webserver.vm.synced_folder "./tomcatwebapps", "/opt/tomcat/webapps"

    webserver.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.name = "webserver-tomcat"
      vb.memory = "1024"
    end
    #
    # View the documentation for the provider you are using for more
    # information on available options.

    # Enable provisioning with a shell script. Additional provisioners such as
    # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
    # documentation for more information about their specific syntax and use.
    # webserver.vm.provision "shell", inline: <<-SHELL
    #   apt-get update
    #   apt-get install -y apache2
    # SHELL
  end


  #défibition d'un second serveur preprod
  config.vm.define "preprodserver" do |preprodwebserver|

    preprodwebserver.vm.box = "bento/ubuntu-22.04"

    #preprodwebserver.vm.box_version = "202404.26.0"

    preprodwebserver.vm.box_check_update = false

    preprodwebserver.vm.network "forwarded_port", guest: 8080, host: 8083

    preprodwebserver .vm.network "private_network", type: "static", ip: "192.168.33.11"

    preprodwebserver.vm.synced_folder "./tomcatwebapps", "/opt/tomcat/webapps"

    preprodwebserver.vm.provider "virtualbox" do |vb|
      vb.gui = false
      vb.name = "preprodwebserver-tomcat"
      vb.memory = "1024"
    end
    #
    # View the documentation for the provider you are using for more
    # information on available options.

    # Enable provisioning with a shell script. Additional provisioners such as
    # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
    # documentation for more information about their specific syntax and use.
    # webserver.vm.provision "shell", inline: <<-SHELL
    #   apt-get update
    #   apt-get install -y apache2
    # SHELL
  end


end
