Ansible playbook: macsetup
=========

[![MIT licensed][mit-badge]][mit-link]

Ansible playbook for MacOS automated configuration

Does the following:

 - Installs [Homebrew][homebrew].
 - Installs custom set of Homebrew packages and applications from Homebrew cask.
 - Configures MacOS Dock.
 - Configures the pf firewall using [drew-kun.pf][pf-galaxy-link] ansible role
 - Configures the [drew-kun.sshd][sshd-galaxy-link] ansible role

Requirements
------------

NOTE: Role requires Fact Gathering by ansible!

MacOS system on configured machine

Playbook Variables
------------------

| Variable | Description | Default |
|----------|-------------|---------|
| **macsetup_homebrew_cask_appdir** | Homebrew cask 'Applications' directory | `~/Applications` |
| **macsetup_homebrew_taps** | List of taps to be used in Homebrew | see [`vars/homebrew.yml`](vars/homebrew.yml) |
| **macsetup_homebrew_installed_packages** | List of packages to be installed from Homebrew | see [`vars/homebrew.yml`](vars/homebrew.yml) |
| **macsetup_homebrew_cask_apps** | List of apps to be installed from Homebrew cask | see [`vars/homebrew.yml`](vars/homebrew.yml) |
| **macsetup_remove_dockitems[]** | Remove only specified dock items. Only used if **macdock_items_remove_all** is set to `no` | see [`vars/dock.yml`](vars/dock.yml) |
| **macsetup_add_dockitems[]** | List of items to be added to dock | see [`vars/dock.yml`](vars/dock.yml) |

Dependencies
------------

 - [elliotweiser.osx-command-line-tools][dep-osx-clt-role]
 - [geerlingguy.homebrew][homebrew-galaxy-link]
 - [feffi.macos-defaults][macos-defaults-role-link]
 - [drew-kun.mas][mas-galaxy-link]
 - [drew-kun.macdock][macdock-galaxy-link]
 - [drew-kun.nerdfonts][nerdfonts-galaxy-link]
 - [drew-kun.terminus_powerline][terminus_powerline-galaxy-link]
 - [drew-kun.macos_terminal][macos_terminal-galaxy-link]
 - [drew-kun.ohmyzsh][ohmyzsh-galaxy-link]
 - [drew-kun.vim][vim-galaxy-link]
 - [drew-kun.mpd][mpd-galaxy-link]
 - [drew-kun.pf][pf-galaxy-link]
 - [drew-kun.sshd][sshd-galaxy-link]

Install via ansible-galaxy:

    ansible-galaxy install -r requirements.yml --force

Example Using Playbook
----------------------

    ansible-playbook --user user1 -k macsetup_playbook.yml

License
-------

[MIT][mit-link]

Author Information
------------------

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[homebrew-galaxy-link]: https://galaxy.ansible.com/geerlingguy/homebrew/
[dep-osx-clt-role]: https://galaxy.ansible.com/elliotweiser/osx-command-line-tools/
[macos-defaults-role-link]: https://github.com/feffi/ansible-macos-defaults
[mas-galaxy-link]: https://galaxy.ansible.com/drew-kun/mas/
[macdock-galaxy-link]: https://galaxy.ansible.com/drew-kun/macdock/
[nerdfonts-galaxy-link]: https://galaxy.ansible.com/drew-kun/nerdfonts/
[terminus_powerline-galaxy-link]: https://galaxy.ansible.com/drew-kun/terminus_powerline/
[macos_terminal-galaxy-link]: https://galaxy.ansible.com/drew-kun/macos_terminal/
[ohmyzsh-galaxy-link]: https://galaxy.ansible.com/drew-kun/ohmyzsh/
[vim-galaxy-link]: https://galaxy.ansible.com/drew-kun/vim/
[mpd-galaxy-link]: https://galaxy.ansible.com/drew-kun/mpd/
[pf-galaxy-link]: https://galaxy.ansible.com/drew-kun/pf/
[sshd-galaxy-link]: https://galaxy.ansible.com/drew-kun/sshd/

[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew-kun/ansible-macos_setup/master/LICENSE
[homebrew]: http://brew.sh/
