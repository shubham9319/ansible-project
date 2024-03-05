# Docker and docker-compose installation setup on Ubuntu

This playbook will install a docker and docker-compose on an Ubuntu machine. Variables are stored in the `vars/docker_vars.yml` variable file.

## Settings
For. ex: vars/docker_vars.yml

- `username`: Add user to docker group.

## Running this Playbook

Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com/shubham9319/ansible-project.git
cd ansible-project/docker_ubuntu/

```

### 2.1. Customize Options

```shell
nano vars/docker_vars.yml
```

```yml
---
username: "ubuntu"
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] docker-setup.yml
```
