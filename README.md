# week6_basic_ansible
week6_basic_ansible
this playbook will create and provision all web servers within the network with the weight tracker app 

https://developer.okta.com/blog/2020/06/01/node-postgres-weight-tracker

#steps
##change ansible.cnf on folder /etc/ansible to allow connection without key exchanges

##change hosts file for different targets

##run ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username>
  
##you can add -vvv to have verbose:
ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> -vvv

##you can add few flags for debugging:  
run ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> --step

the last command will ask you to confirm each step

run ansible-playbook -i hosts <location of the hosts> <location of playbook> -u <username> --start-at-task:"<name of the task>"
  
the last command will start the playbook on the requested task name

#you can mix and use the commands all together
