# ansibleNginx
#This script was created using Vagrant 2.1.2 & Ansible 2.6.4

On a machine with Vagrant & Ansible installed, clone the repo and simply type "vagrant up". It will deploy an Ubuntu Nginx server that will load balance traffic between 2 CentOS servers running Apache. Browse to http://192.168.33.20/ and refresh and you will see it swap between both nodes
