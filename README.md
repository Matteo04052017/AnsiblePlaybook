# AnsiblePlaybook
This playbook allows to create a minimum but complete TANGO-controls develoment environemnt.

Steps to make it work with SSH:
1. Edit the file "hosts" with the address(es) to want to manage. (if not localhost)
2. Add the ssh key to the managed hosts (if not localhost). 
3. Install ansible::
    apt-add-repository --yes --update ppa:ansible/ansible && apt-get install ansible
4. Lunch ansible:: 
    ansible-playbook -i hosts deploy_tangoenv.yml

Steps to make it work without SSH (deprecatred):
1. Install ansible::
    apt-add-repository --yes --update ppa:ansible/ansible && apt-get install ansible
2. Lunch ansible:: 
        ansible-playbook -i hosts deploy_tangoenv.yml -u USERNAME --ask-pass --ask-sudo-pass

To work with pytango, do the following steps:
1. source /venv/bin/activate
2. pipenv shell
