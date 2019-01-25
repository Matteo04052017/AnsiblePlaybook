# AnsiblePlaybook
This playbook allows to create a minimum but complete TANGO-controls develoment environemnt.

Steps to make it work with RSA KEY:
1. Edit the file "hosts" with the address(es) to want to manage (if not localhost).
2. Add the ssh key to the managed hosts (if not localhost). 
3. Install ansible:
``` 
    apt-add-repository --yes --update ppa:ansible/ansible && apt-get install ansible
```
4. Lunch ansible:
``` 
    ansible-playbook -i hosts deploy_tangoenv.yml 
```
or with password: 
```
    ansible-playbook -i hosts deploy_tangoenv.yml --extra-vars "ansible_become_pass=*password*"
```

To work with pytango, activate the virtualenv:
``` 
    source /venv/bin/activate
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

TESTED OS:
* ubuntu:16.04
* debian:stretch-slim