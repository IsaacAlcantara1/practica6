Vagrant.configure("2") do |config|

    config.vm.define "web1" do |web1|
      web1.vm.box = "ubuntu/bionic64"
      web1.vm.network "private_network", ip: "192.168.56.160"
      web1.vm.hostname = "web1"
      web1.vm.synced_folder "./html", "/var/www/html"
      
      web1.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y apache2
        systemctl enable apache2
      SHELL
    end
  
    config.vm.define "web2" do |web2|
      web2.vm.box = "ubuntu/bionic64"
      web2.vm.network "private_network", ip: "192.168.56.168"
      web2.vm.hostname = "web2"
      web2.vm.synced_folder "./html", "/var/www/html"
      
      web2.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y apache2
        systemctl enable apache2
      SHELL
    end
  
  end
  