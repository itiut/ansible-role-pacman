itiut.pacman ![build status](https://circleci.com/gh/itiut/ansible-role-pacman.svg?style=shield&circle-token=ed53438e0d0f0753da94078600c4b24af7ba2452)
====

Ansible role for installing pacman packages.

Requirements
----

- Python 2
- Ansible 1.9 or higher

Role Variables
----

Role variables are in [defaults/main.yml](defaults/main.yml).

#### `pacman_update` (default: `true`)

Whether to update caches or not: `true` or `false`.

#### `pacman_install_state` (default: `present`)

A state of installing (or installed) packages: `present` or `latest`.

#### `pacman_install` (default: `[]`)

An array of packages to install.

#### `pacman_remove` (default: `[]`)

An array of packages to remove.

Example Playbook
----

```yaml
- hosts: localhost
  vars:
    pacman_install:
    - emacs
    - vim
    - zsh
  roles:
  - { role: itiut.pacman, tags: pacman }
```

Notes
----

`python2` is required to run Ansible 1.9 but `python` is linked to `python3` on Arch Linux. So setting `ansible_python_interpreter` to `python2` is required.

In inventory:

```
[localhost:vars]
ansible_python_interpreter=python2
```

Or in playbook:

```yaml
- host: localhost
  vars:
    ansible_python_interpreter: python2
```

License
----

MIT
