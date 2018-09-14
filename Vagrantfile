#Vagrant config file(Vagrantfile)
Vagrant.configure("2") do |config|

  config.vm.define "lb1" do |lb1|
    lb1.vm.box = "nrel/CentOS-6.5-x86_64"
    lb1.vm.hostname = "lb1"
    lb1.vm.network "private_network", ip: "192.168.33.20"
  end

  config.vm.define "web01" do |web01|
    web01.vm.box = "nrel/CentOS-6.5-x86_64"
    web01.vm.hostname = "web01"
    web01.vm.network "private_network", ip: "192.168.33.50"
    web01.vm.network "forwarded_port", guest: 80, host: 8080
  end

  config.vm.define "web02" do |web02|
    web02.vm.box = "nrel/CentOS-6.5-x86_64"
    web02.vm.hostname = "web02"
    web02.vm.network "private_network", ip: "192.168.33.51"
    web02.vm.network "forwarded_port", guest: 80, host: 8081
  end
  #
  # Run Ansible from the Vagrant Host
  #
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbooks/web_lb.yml"
    ansible.groups = { 
      "webservers" => ["web01", "web02"],
      "lbservers" => ["lb1"]
    }
  end
end