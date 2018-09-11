# ansibleNginx

Vagrantfile can be used to deploy an Ubuntu server(acs) and 3 CentOS VM's LB1, WEB01, and WEB02. If you install Ansible and have kept the original directory structure you can execute playbook web_lb.yml to install an nginx load balancer on lb1 that load balances traffic between web01 & web02. You can test the load balancer by going to http://192.168.33.20 and hitting refresh.


The ansible server must have sshpass installed and added the keys from each server, otherwise ansible will be unable to connect to the remote servers. (you can add the keys from the acs server by typing "ssh vagrant@ip" and typing yes to accept the key). Once the key has been accepted you can push Ctrl+C as there is no need to authenticate with the server after the key has been accepted

start the playbook with: "ansible-playbook web_lb.yml"
