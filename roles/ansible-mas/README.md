Ansible role: macdock
=========

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Ansible role for programmatic MacOS Dock customization.

Requirements
------------

MacOS on the configured host.

Role Variables
--------------

| Variable | Description | Default |
|----------|-------------|---------|
| **macdock_hide** | Automatically hide/show dock? | `no` |
| **macdock_magnify** | Use dock magnify effect? | `no` |
| **macdock_items_remove_all** | Remove all currently configured items from dock before dock customization | `no` |
| **macdock_remove_items[]** | Remove only specified dock items. Only used if **macdock_items_remove_all** is set to `no` | see [`defaults/main.yml`](defaults/main.yml) |
| **macdock_add_items[]** | List of items to be added to dock | see [`vars/Debian.yml`](vars/Debian.yml) |

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: dev_clients
  roles:
  - role: drew-kun.macdock
```

License
-------

[MIT][mit-link]

Author Information
------------------

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[role-badge]: https://img.shields.io/badge/role-drew--kun.macdock-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew-kun/macdock/

[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew-kun/ansible-macos_setup/master/LICENSE
