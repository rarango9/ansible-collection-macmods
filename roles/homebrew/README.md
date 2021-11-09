# Homebrew

Install Homebrew and manage packages, taps and casks.

## Requirements

- `homebrew`: The Missing Package Manager for macOS (or Linux).

## Role Variables

```yaml
# Parent directory that Homebrew will be installed to.
homebrew_prefix: "{{ (ansible_machine == 'arm64') | ternary('/opt/homebrew', '/usr/local') }}"

# Homebrews installation directory, in this case the cloned repository.
homebrew_repository: "{{ homebrew_prefix }}/Homebrew"

# By default homebrew/core is tapped, add any other repositories to tap here.
homebrew_taps_install: []
# - name: hashicorp/tap
#   url: https://github.com/hashicorp/homebrew-tap
# - hashicorp/tap

# Remove any repositories that are tapped.
homebrew_taps_remove: []
# - hashicorp/tap

# List of Homebrew packages to install.
homebrew_packages_install: []
# - git
# - name: git
#   state: latest

# List of Homebrew packages to remove.
homebrew_packages_remove: []
# - groovy

# Should all installed Homebrew packages be upgraded.
homebrew_packages_upgrade_all: no

# List of Homebrew cask apps to install.
homebrew_casks_install: []
# - google-chrome
# - name: google-chrome
#   state: latest
#   greedy: yes

# List of Homebrew cask apps to remove.
homebrew_casks_remove: []
# - alfred
# - wireshark

# Should all installed Homebrew cask apps be upgraded.
homebrew_casks_upgrade_all: no

# URL to the Homebrew/brew repository.
homebrew_repo_url: https://github.com/Homebrew/brew

# Homebrew subdirectories list.
homebrew_directories:
  - Cellar
  - Homebrew
  - Frameworks
  - Caskroom
  - bin
  - etc
  - include
  - lib
  - opt
  - sbin
  - share
  - share/zsh
  - share/zsh/site-functions
  - var

```

## Dependencies

- `rarango9.command_line_tools`
- `community.general`

## Example Playbook

```yaml
- hosts: localhost

  vars:
    homebrew_packages_install:
      - name: git
        state: latest
    
    homebrew_casks_upgrade_all: yes

  roles:
    - rarango9.command_line_tools
    - rarango9.homebrew
```

## License

MIT

## Author Information

Created by Rob Arango as part of the MacMods Ansible Collection.
