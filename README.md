# AnsiblePlaybook
This playbook allows to create a minimum but complete TANGO-controls develoment environemnt.

TESTED OS:
*. ubuntu:16.04

Steps to make it work with SSH:
1. Edit the file "hosts" with the address(es) to want to manage. (if not localhost)
2. Add the ssh key to the managed hosts (if not localhost). 
3. Install ansible:
``` 
    apt-add-repository --yes --update ppa:ansible/ansible && apt-get install ansible
```
4. Lunch ansible:
``` 
    ansible-playbook -i hosts deploy_tangoenv.yml
```
Steps to make it work without SSH (deprecatred):
1. Install ansible:
``` 
    apt-add-repository --yes --update ppa:ansible/ansible && apt-get install ansible
```
2. Lunch ansible:: 
``` 
    ansible-playbook -i hosts deploy_tangoenv.yml -u USERNAME --ask-pass --ask-sudo-pass
```
To work with pytango, do the following steps:
``` 
    source /venv/bin/activate
    pipenv shell
```

The following variables can be set:
```
    build_tango: default('yes')
    build_mysql: default('yes')
    install_pytango: default('yes')
    install_ide: default('yes')
```

For example:
```
    ansible-playbook -i hosts deploy_tangoenv.yml --extra-vars "build_tango='no' build_mysql='no' install_ide='no'"
```