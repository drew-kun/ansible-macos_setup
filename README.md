Ansible playbook: macsetup
=========

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Ansible playbook for MacOS automated configuration

Does the following:

 - Installs [Homebrew][homebrew].
 - Installs custom set of Homebrew packages and applications from [caskroom][caskroom].
 - Configures MacOS Dock.
 - Configures the pf firewall using [drew_kun.pf][pf-role-link] ansible role
 - Configures the [drew_kun.sshd][sshd-role-link] ansible role

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
 - [drew_kun.homebrew][homebrew-galaxy-link]
 - [drew_kun.macdock][macdock-galaxy-link]
 - [drew_kun.terminus_powerline][terminus_powerline-galaxy-link]
 - [drew_kun.nerdfonts][nerdfonts-galaxy-link]
 - [drew_kun.macos_terminal][macos_terminal-galaxy-link]
 - [drew_kun.ohmyzsh][ohmyzsh-galaxy-link]
 - [drew_kun.pf][pf-galaxy-link]
 - [drew_kun.sshd][sshd-galaxy-link]

Install via ansible-galaxy:

    ansible-galaxy install elliotweiser.osx-command-line-tools \
                           drew_kun.homebrew \
                           drew_kun.macdock \
                           drew_kun.nerdfonts \
                           drew_kun.terminus_powerline\
                           drew_kun.macos_terminal \
                           drew_kun.ohmyzsh \
                           drew_kun.pf \
                           drew_kun.sshd

Example Using Playbook
----------------------

    ansible-playbook --user user1 -k macsetup_playbook.yml

License
-------

[MIT][mit-link]

Author Information
------------------

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[homebrew-galaxy-link]: https://galaxy.ansible.com/drew_kun/homebrew/
[dep-osx-clt-role]: https://galaxy.ansible.com/elliotweiser/osx-command-line-tools/
[macdock-galaxy-link]: https://galaxy.ansible.com/drew-kun/macdock/
[nerdfonts-galaxy-link]: https://galaxy.ansible.com/drew-kun/nerdfonts/
[terminus_powerline-galaxy-link]: https://galaxy.ansible.com/drew-kun/terminus_powerline/
[macos_terminal-galaxy-link]: https://galaxy.ansible.com/drew-kun/macos_terminal/
[ohmyzsh-galaxy-link]: https://galaxy.ansible.com/drew-kun/ohmyzsh/
[pf-galaxy-link]: https://galaxy.ansible.com/drew-kun/pf/
[sshd-galaxy-link]: https://galaxy.ansible.com/drew-kun/sshd/

[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew_kun/ansible-macos_setup/master/LICENSE
[homebrew]: http://brew.sh/
[caskroom]: https://caskroom.github.io/search
