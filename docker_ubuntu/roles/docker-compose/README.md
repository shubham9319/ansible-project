# docker-compose installation setup on Ubuntu

This role will install a docker-compose on an Ubuntu machine. Variables are stored in the `vars/main.yml` variable file.

## Settings
For. ex: roles/docker-compose/vars/main.yml

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
nano roles/docker-compose/vars/main.yml
```

```yml
---
username: "ubuntu"
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] docker-compose.yml
```
