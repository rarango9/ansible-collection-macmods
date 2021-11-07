# Command Line Tools

Installs MacOS Command Line Tools.

## Requirements

*NONE*

## Role Variables

```yaml
# Force installation of MacOS Command Line Tools even if already installed.
clt_force_install: no
```

## Dependencies

*NONE*

## Example Playbook

```yaml
- hosts: localhost

  vars:
    clt_force_install: yes

  roles:
    - rarango9.command-line-tools
```

## License

MIT

## Author Information

Created by Rob Arango as part of the MacMods Ansible Collection.
