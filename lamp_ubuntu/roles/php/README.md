# Apache on Ubuntu

This playbook will install the PHP on an Ubuntu machine. Variable changes will be done in `vars/main.yml` variable file.

## Settings

For. ex: roles/php/vars/main.yml

- `http_host`: your domain name.

## Running this Playbook

Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com/shubham9319/ansible-project.git
cd ansible-project/lamp_ubuntu/
```

### 2. Customize Options

```shell
nano roles/php/vars/main.yml
```

```yml
---
http_host: "your_domain"
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] php_role.yml
```
