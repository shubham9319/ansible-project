# Apache on Ubuntu

This playbook will install the MySQL database on a Ubuntu machine. Variable changes will be done in the `vars/main.yml` variable file.

## Settings

For. ex: roles/mysql/vars/main.yml

- `mysql_root_password`: the password for the MySQL root account.

## Running this Playbook

Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com/shubham9319/ansible-project.git
cd ansible-project/lamp_ubuntu/
```

### 2. Customize Options

```shell
nano roles/mysql/vars/main.yml
```

```yml
---
mysql_root_password: "Password"
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] mysql_role.yml
```
