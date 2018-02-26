Ansible role: macos_setup
=========

[![MIT licensed][mit-badge]][mit-link]
[![Galaxy Role][role-badge]][galaxy-link]

Ansible role configures MacOS using [Homebrew][homebrew], installs applications from cask and sets up dock.

Requirements
------------

One of the following OS (or deriviatives):
  - MacOS

Role Variables
--------------

    # Homebrew
    macos_setup_homebrew_upgrade_all_packages: yes | no             # Does brew upgrade if homebrew is already installed
    macos_setup_homebrew_use_brewfile: yes                          # Uses brewfile for Homebrew (like Gemfile for ruby)
    macos_setup_homebrew_brewfile_dir: '~'                          # Where to look for brewfile
    macos_setup_homebrew_cask_appdir: "{{ homebrew_cask_appdir }}"  # By default: ~/Applications
                                                                    # This var comes from drew-kun.homebrew role

    macos_setup_homebrew_installed_packages:                        # List of packages to be installed from homebrew
    - pkg: dockutil                                                 # Package name
        install_opts: []                                            # List of Homebrew install options for that package

    macos_setup_homebrew_uninstalled_packages: []                   # List of packages to be removed

    macos_setup_homebrew_cask_apps: []                              # List of casks to be installed
    macos_setup_homebrew_uninstalled_cask_apps: []                  # List of casks to be removed

    # MacOS Dock
    macos_setup_dockitems_to_remove:                                # List of items to be removed from MacOS Dock
    - "Calendar"
    - "'App Store'"                                                 # NOTE: names containing spaces must be quoted twice

    macos_setup_dockitems_to_persist: []
    - app: "'Google Chrome'"                                        # NOTE: names containing spaces must be quoted twice
      path: "{{ homebrew_cask_appdir }}/'Google Chrome.app'"        # Path to the app
      pos: 2                                                        # Position number in Dock (left to right)


Dependencies
------------

 - [drew-kun.homebrew][homebrew-galaxy-link]

Install via ansible-galaxy:

    ansible-galaxy install drew-kun.homebrew

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: dev_clients
      roles:
         - role: drew-kun.macos_setup

License
-------

[MIT][mit-link]

Author Information
------------------

Andrew Shagayev | [e-mail](mailto:drewshg@gmail.com)

[role-badge]: https://img.shields.io/badge/role-drew--kun.macos__setup-green.svg
[galaxy-link]: https://galaxy.ansible.com/drew-kun/macos_setup/
[homebrew-galaxy-link]: https://galaxy.ansible.com/drew-kun/homebrew/

[mit-badge]: https://img.shields.io/badge/license-MIT-blue.svg
[mit-link]: https://raw.githubusercontent.com/drew-kun/ansible-macos_setup/master/LICENSE
[homebrew]: http://brew.sh/
