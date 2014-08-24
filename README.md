osx-login-shell
===============

An Ansible role to set the login shell on OS X

Requirements
------------

If the value of the variable osx_login_shell_shell is not in /etc/shells,
you need to run ansible-playbook with -K (ask_sudo_pass) option
in order to add a line to /etc/shells.

```
ansible-playbook -K _your_playbook_.yml
```

You will be prompted for entering your password for sudo.

Also if the current shell is different from the value of the variable osx_login_shell_shell,
you will be prompted for entering your password to change the login shell.

Role Variables
--------------

- osx_login_shell_shell: /bin/zsh

Dependencies
------------

None.

Example Playbook
----------------

### Example 1

    - hosts: servers
      roles:
         - hnakamur.osx-login-shell

### Example 2: with parameter

    - hosts: servers
      roles:
         - { role: hnakamur.osx-login-shell, osx_login_shell_shell: '/usr/local/bin/zsh' }

License
-------

MIT

Author Information
------------------

[Hiroaki Nakamura]( http://hnakamur.github.io/ )
