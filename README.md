ssh
===

[![Build Status](https://travis-ci.org/jebovic/ansible-ssh.svg?branch=master)](https://travis-ci.org/jebovic/ansible-ssh) [![Ansible Galaxy](https://img.shields.io/badge/galaxy-jebovic.ssh-blue.svg?style=flat)](https://galaxy.ansible.com/jebovic/ssh)

Install and configure SSH server

This role is a part of my [OPS project](https://github.com/jebovic/ops), follow this link to see it in action. OPS provides a lot of stuff, like a vagrant file for development VMs, playbooks for roles orchestration, inventory files, examples for roles configuration, ansible configuration file, and many more.

Compatibility
-------------

Tested and approved on :

* Debian jessie (8+)
* Ubuntu Trusty (14.04 LTS)
* Ubuntu Xenial (16.04 LTS)

Role Variables
--------------

```yaml
# Install configuration
ssh_packages:
    - openssh-server
    - openssh-client
    - sudo

# SSH server configuration
sshd_config_file: /etc/ssh/sshd_config
sshd_port: 22

# User configuration
admin_user: ops
admin_user_group: admin
admin_authorized_key: "{{ lookup('file', '~/.ssh/id_rsa.pub') }}"
admin_shell: /bin/bash
admin_user_sudoer: yes
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - { role: jebovic.ssh }
```

Example : config
----------------

```yaml
# chang ssshd port binding
sshd_port: 2222
# Admin user configuration
admin_user: me
admin_user_group: me
admin_authorized_key: "{{ lookup('file', '~/.ssh/my_rsa.pub') }}"
admin_shell: /bin/zsh
admin_user_sudoer: yes
```

Tags
----

* ssh_config : only update config and restart service

License
-------

MIT

Author Information
------------------

Jérémy Baumgarth https://github.com/jebovic
