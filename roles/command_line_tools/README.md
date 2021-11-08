# Command Line Tools

Installs MacOS Command Line Tools.

## Requirements

*NONE*

## Role Variables

```yaml
# Force installation of MacOS Command Line Tools even if already installed.
command_line_tools_force_install: no
```

## Dependencies

*NONE*

## Example Playbook

```yaml
- hosts: localhost

  vars:
    command_line_tools_force_install: yes

  roles:
    - rarango9.command_line_tools
```

## License

MIT

## Author Information

Created by Rob Arango as part of the MacMods Ansible Collection.
