# AnsiblePlaybook
This playbook allows to create a minimum but complete TANGO-controls develoment environemnt.

Steps to make it work with SSH:
* Edit the file "hosts" with the address(es) to want to manage. (if not localhost)
* Add the ssh key to the managed hosts (if not localhost). 
* Install ansible::
    apt-add-repository --yes --update ppa:ansible/ansible && apt-get install ansible
* Lunch ansible:: 
    ansible-playbook -i hosts deploy_tangoenv.yml

Steps to make it work without SSH (deprecated):
* Install ansible::
    apt-add-repository --yes --update ppa:ansible/ansible && apt-get install ansible
* Lunch ansible:: 
        ansible-playbook -i hosts deploy_tangoenv.yml -u USERNAME --ask-pass --ask-sudo-pass

To work with pytango, do the following steps:
* source /venv/bin/activate
* pipenv shell
