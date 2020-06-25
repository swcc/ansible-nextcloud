Nextcloud Ansible role
=========

[![Build Status](https://travis-ci.org/swcc/ansible-nextcloud.svg?branch=master)](https://travis-ci.org/swcc/ansible-nextcloud) [![Ansible Galaxy](https://img.shields.io/badge/role-swcc.ansible__nextcloud-blue.svg)](https://galaxy.ansible.com/swcc/ansible-nextcloud)

Installs nextcloud from [nextcloud.com servers](https://download.nextcloud.com/) sources. This role assumes you will run nextcloud with `PHP-FPM` and thus installs it for you as an ansible role dependency (with the [`NBZ4live.php-fpm`](https://github.com/NBZ4live/ansible-php-fpm) role.

Example Playbook
----------------

Basic example playbook:

```yaml
- hosts: webservers
  roles:
    - role: swcc.nextcloud
      nextcloud_destination: /home/nextcloud
      nextcloud_version: 18.0.4
```

Role parameters
----------------

| Variable                | Default    | Type            | Description                                                                                                            |
| ----------------------- | :------:   | :-------------: | ------------                                                                                                           |
| `nextcloud_version`     | `18.0.4`   | `string`        | Which nextcloud version to install                                                                                     |
| `nextcloud_destination` | `/var/www` | `string`        | Where to install Nextcloud (will be installed in "{{ nextcloud_destination}}/nextcloud/" directory on your filesystem) |
| `nextcloud_dir_user`    | `www-data` | `string`        | Which unix user should own the installed directory                                                                     |
| `nextcloud_dir_group`   | `www-data` | `string`        | Which unix group should own the installed directory                                                                    |

_⚠️ Please check the php-fpm variables of the dependent [php-fpm ansible role](https://github.com/NBZ4live/ansible-php-fpm#role-variables) before running this current role. ⚠️_

Makefile for easier Ansible usage
------------------

I have written a small Makefile to make your future ansible runs easier. Don't hesitate to [check it out](https://github.com/paulRbr/ansible-makefile/).

Download the `*.deb` package from the github releases, install it and start using it with `ansible-make help`.

License
-------

GPLv3
