# AnsiblePlaybook
This playbook allows to create a minimum but complete TANGO-controls develoment environemnt.

Steps to make it work:
1) Edit the file "hosts" with the address(es) to want to manage. 
2) Add the ssh key to the managed hosts (if not localhost). 
3) Lunch ansible: "ansible-playbook -i hosts deploy_tangoenv.yml"

To work with pytango, do the following steps:
1) source /venv/bin/activate
2) pipenv shell
