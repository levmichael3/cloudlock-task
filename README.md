# Cloudlock task

 
Task steps:
 
1. Create New EC2 instance (ubuntu 16.04 based)
2. Update the OS with latest security patches
3. Install nginx and enable on boot
4. Verify service is up

# Comment
- Static ami for Ubuntu 16.04 used
 

# Steps used for configurations

- boto for dynamic inventory

# Features

 - health check uses nginx which should return an OK status as well as the string &quot;Everything
works (&lt;name of the current environment&gt;)&quot; when reaching the path /health
 - Ansible playbook Should supports multiple environments (dev, prod)



# Examples
 Flow of usage
 
```sh
$ ENV=<environment>
$ ansible-playbook -v -i localhost, -e "env=$ENV" provision.yml
$ ansible-playbook -v -e "env=$ENV"  -e 'ansible_python_interpreter=/usr/bin/python3' update-os.yml
$ ansible-playbook -v -e "env=$ENV"  -e 'ansible_python_interpreter=/usr/bin/python3' webserver.yml
$ ansible-playbook  -e "env=$ENV"  -e 'ansible_python_interpreter=/usr/bin/python3' verify_nginx.yml

```




### Todos

 - Add private subnets
 - Add Backends
 - .......

License
----

FREE


# cloudlock-task
