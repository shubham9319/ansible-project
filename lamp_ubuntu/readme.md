# LAMP on Ubuntu

This playbook will install a LAMP environment (Linux, Apache, MySQL, and PHP) on an Ubuntu machine. A virtual host will be created with the options specified in the `vars/main.yml` variables files in every roles directory respectively.

## Settings
For. ex: roles/apache/vars/main.yml

- `app_user`: a remote non-root user on the Ansible host that will own the application files.
- `http_host`: your domain name.
- `http_conf`: the name of the configuration file that will be created within Apache.
- `http_port`: HTTP port, default is 80.
- `disable_default`: whether or not to disable the default Apache website. When set to true, your new virtual host should be used as the default website. The default is true.


For. ex: roles/mysql/vars/main.yml

- `mysql_root_password`: the password for the MySQL root account.

For. ex: roles/php/vars/main.yml

- `http_host`: your domain name.

## Running this Playbook

Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com/shubham9319/ansible-project.git
cd ansible-project/lamp_ubuntu/

```

### 2.1. Customize Options

```shell
nano roles/apache/vars/main.yml
```

```yml
---
app_user: "sammy"
http_host: "your_domain"
http_conf: "your_domain.conf"
http_port: "80"
disable_default: true
```

### 2.2. Customize Options

```shell
nano roles/mysql/vars/main.yml
```

```yml
---
mysql_root_password: "Password"
```

### 2.3. Customize Options

```shell
nano roles/php/vars/main.yml
```

```yml
---
http_host: "your_domain"
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] lamp_setup.yml
```
