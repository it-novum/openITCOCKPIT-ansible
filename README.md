[![Build Status](https://travis-ci.org/it-novum/openITCOCKPIT-ansible.svg?branch=master)](https://travis-ci.org/it-novum/openITCOCKPIT-ansible)

Description
-----------

Ansible role which installs and configures openITCOCKPIT v3.


Dependencies
------------

- Ansible 2.0 or higher.
- Tested on Ubuntu 14.04.

Quickstart
----------

- Copy your ssh key to the target host and make sure you can login passwordless
- Create a `playbook.yml` file, containing the following

```yaml
---
- hosts: all
  remote_user: root
  become: true
  become_method: sudo
  become_user: root

  vars:
    user_firstname: root
    user_surname: wheel
    user_email: root@example.com
    user_password: oitcsuperpassword
    phpnsta_user_name: phpnsta
    phpnsta_user_password: phpnstasuperpassword

  roles:
      - it-novum.openITCOCKPIT-ansible
```

- Fetch this role with dependencies `ansible-galaxy install -p . it-novum.openITCOCKPIT-ansible`
- Run the playbook with `ansible-playbook playbook.yml -i "127.0.0.1"`
- Login to Graylog by opening `http://localhost` in your browser

Variables
--------

```yaml
production: no
os: trusty

db_name: openitcockpit
db_user: oitc
db_user_password: mysql_password
db_root_password: root_password

mailserver: localhost
smtpport: 25
senderaddress: root@example.com

user_firstname: root
user_surname: wheel
user_email: root@example.com
user_password: oitcsuperpassword

phpnsta_user_name: phpnsta
phpnsta_user_password: phpnstasuperpassword

#wkhtmltopdf variables
wk_os: trusty
wk_arch: amd64
wk_version: 0.12.3
wk_version_major: 0.12

```

Take a look into `defaults/main.yml` to get an overview of all configuration parameters

License
-------

Authors: Sascha Veres (<sascha.veres@it-novum.com>), Daniel Ziegler (<daniel.ziegler@it-novum.com>) and [contributors](https://github.com/it-novum/openITCOCKPIT-ansible/graphs/contributors)

License: MIT