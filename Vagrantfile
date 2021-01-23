$script_mongo = <<-SCRIPT
  sudo touch /etc/yum.repos.d/mongodb-org-4.4.repo
  echo [mongodb-org] >> /etc/yum.repos.d/mongodb-org-4.4.repo
  echo name=MongoDB Repository >> /etc/yum.repos.d/mongodb-org-4.4.repo
  echo baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.4/x86_64/ >> /etc/yum.repos.d/mongodb-org-4.4.repo
  echo gpgcheck=1 >> /etc/yum.repos.d/mongodb-org-4.4.repo
  echo enabled=1 >> /etc/yum.repos.d/mongodb-org-4.4.repo
  echo gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc >> /etc/yum.repos.d/mongodb-org-4.4.repo
  sudo yum install -y mongodb-org
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  #config.vm.network "forwarded_port", guest: 80, host: 8089
  #config.vm.network "private_network", ip: "192.168.10.4"
  config.vm.provision "shell", inline: $script_mongo
end
