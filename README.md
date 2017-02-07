Kodi Media Center Role for Ansible
==================================

This is a simple Ansible role that configures a Linux system
for use as a Media Center.

It creates a kodi user, installs all the necessary packages
and sets up login-less and desktop-less login.

At the time of creation, this role was primarily made for
Debian stretch, but can also be used for other recent
Debian-based distributions, such as Ubuntu 16.04 (or later).


Copyright
---------

All files in this Ansible role are
Copyright © 2017 Gregor Riepl <onitake@gmail.com>

All rights reserved.

Released under the ISC license.
See the LICENSE file for details on permitted usage.

Mostly based on:
http://www.richud.com/wiki/Ubuntu_Minimal_KODI_Install


Usage
-----

To use this role in your own playbooks, import it using `ansible-galaxy`.

Create a file named `install_roles.yml` in your Ansible project
with the following contents:

```yaml
- src: https://github.com/onitake/ansible-role-kodi
  name: kodi
```

Install the role:

```bash
ansible-galaxy install -r install_roles.yml
```

To use the role in a playbook, simply specify it as:

```yaml
- hosts: kodi
  roles:
  - kodi
```


Variables
---------

Two variables can be overridden in your inventory,
`kodi_user` and `kodi_group`.

They are both set to "kodi" by default and determine the user
kodi will be run as. All necessary permissions required for
this user are set by the role.
