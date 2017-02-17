# opstools-gate
collection of playbooks to test CentOS opstools SIG packages

The playbook will launch a VM on an OpenStack instance.

# Using opstools-gate
## creating an inventory file

Create or modify the file `inventory/hosts`:

    testvm ansible_host=192.168.1.1 ansible_user=centos ansible_become=true
  
## creating a config.yml

    project_name: changeme
    username: changeme
    password: changeme
    auth_url: https://192.168.1.100:5000/v2.0
    vm_name: 
    image_uuid:
    
vm_name can be set, it's the name for the vm to be used, you need to define the image uuid of the image to be launched.

# Run the playbook
Finally, you're ready to run the playbook like this:

    ansible-playbook playbook.yml -e @config.yml
