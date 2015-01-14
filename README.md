ansible-lemp
=========

> [Ansible](http://www.ansible.com) role to install the LEMP stack in Ubuntu Trusty.

Requirements
------------

None.

Role Variables
--------------

- `lemp_upload_max_filesize`: value of variable `upload_max_filesize` in php.ini, by default 10M
- `lemp_post_max_size`: value of variable `post_max_size` in php.ini, by default 12M

Dependencies
------------

This role depends on the roles `larixsource.ec2-mysql` and `azavea.nginx`.

Example Playbook
----------------

```yml
- hosts: servers
  vars:
    - mysql_use_ebs: true
    - mysql_ebsdev: 'xvdg'
    - mysql_root_password: 'supersecret'
    - nginx_delete_default_site: true
    - lemp_upload_max_filesize: 10M
    - lemp_post_max_size: 22M
  roles:
     - larixsource.lemp
```

Also, there's an example of provisioning with Vagrant in a local VM in the directory `test`.

License
-------

Apache-2.0

Author Information
------------------

Courtesy of [Larix](http://www.larix.cl) team.
