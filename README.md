ssh
===

[![Build Status](https://travis-ci.org/jebovic/ansible-ssh.svg?branch=master)](https://travis-ci.org/jebovic/ansible-ssh) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.ssh-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/ssh)

Install and configure SSH server

Role Variables
--------------

```
# SSH server configuration
sshd_config_file: /etc/ssh/sshd_config
sshd_port: 22

# User configuration
admin_user: ops
admin_user_group: admin
admin_authorized_key: "{{ lookup('file', '~/.ssh/id_rsa.pub') }}"
admin_shell: /bin/bash
```

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: jebovic.ssh }
```

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
