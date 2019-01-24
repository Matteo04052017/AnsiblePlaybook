# AnsiblePlaybook
This playbook allows to create a minimum but complete TANGO-controls develoment environemnt.

Steps to make it work:
1) Edit the file "hosts" with the address(es) to want to manage. 
2) Add the ssh key to the managed hosts. 
3) Lunch ansible: "ansible-playbook -i hosts deploy_tangoenv.yml"


