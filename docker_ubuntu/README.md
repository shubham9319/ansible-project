Author: Shubham Shinde

This is an ansible project used to install/configure docker and docker-compose on remote servers.

File1: docker-setup.yml:
This main ansible playbook file is used to install and configure docker and docker-compose on the remote server.

File2: docker_vars.yml:
This is an environment variable file to pass variable values. For ex: username=ubuntu. Change Ubuntu to your respective username.

File3: inventory.yml:
This is an inventory file to store remote hosts' details. For ex: Remote host IP Address like 10.10.10.10
