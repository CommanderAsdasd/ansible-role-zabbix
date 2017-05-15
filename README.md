# README.md
# Ansible Role: mats116.zabbix forked

An Ansible role that installs Zabbix 3.0alpha4 on **Ubuntu 14.04 LTS** - fixed php-fpm5.6 name changed bugs 

## Requirements

none

## Role Variables

Available variables are listed below, along with default values:

```yaml
zabbix_version: "3.0.0alpha4"

zabbix_user: zabbix
zabbix_group: zabbix
zabbix_home: /etc/zabbix

zabbix_nginx_accesslog: /var/log/nginx/zabbix-access.log

zabbix_mysql_host: localhost
zabbix_mysql_database: zabbix
zabbix_mysql_user: zabbix
zabbix_mysql_password: zabbix
```

## Dependencies

- [mats116.nginx](https://galaxy.ansible.com/detail#/role/6198) - Installer of Nginx
- [mats116.php5-fpm](https://galaxy.ansible.com/detail#/role/6238) - Installer of php-fpm
- [mats116.mariadb-server](https://galaxy.ansible.com/detail#/role/6199) - Installer of MariaDB Server (MySQL)
 - `when "zabbix_mysql_host == 'localhost'"`

## Example Playbook

```yaml
- hosts: zabbix-server
  roles:
    - role: mats116.zabbix
```

## License

MIT
