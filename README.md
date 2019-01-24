# AnsiblePlaybook
This playbook allows to create a minimum but complete TANGO-controls develoment environemnt.

First of all, edit the file "hosts" with the address(es) to want to manage.

Once done you can call:
ansible-playbook -i hosts deploy_tangoenv.yml

