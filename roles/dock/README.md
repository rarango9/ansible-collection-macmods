# Dock

Manage preferences and items on the MacOS Dock to automate the configuration.

## Requirements

- `homebrew`: The Missing Package Manager for macOS (or Linux).
- `dockutil`: A command line utility for managing MacOS dock items.

## Role Variables

```yaml
# Whether to make the dock hidden.
# Options: yes|no
# Default: yes
dock_autohide: yes

# Position of the dock on the screen.
# Options: bottom|left|right
# Default: bottom
dock_screen_position: bottom

# Minimize applications to dock using an effect.
# Options: genie|scale|suck
# Default: genie
dock_minimize_effect: genie

# Size of the dock items.
# Options: Integer between 16-128
# Default: 64
dock_tile_size: 64

# Enable magnification of dock items on mouseover.
# Options: yes|no
# Default: no
dock_magnification: no

# Magnification size on mouseover. Only used when dock_magnification is yes.
# Options: Integer between 16-128
# Default: 64
dock_magnification_size: 128

# Minimize windows into application icon.
# Options: yes|no
# Default: yes
dock_minimize_into_application_icon: yes

# Show process indicators below the dock items.
# Options: yes|no
# Default: yes
dock_show_process_indicators: yes

# Remove dock items based on label name.
# Options: List of dock item labels
# Default: Empty List
dock_remove_items: []
# - Launchpad
# - Apple TV

# Persist dock items and optionally order items.
# Options: List of dock items with label, path and pos (optional) properties.
# Default: Empty List
dock_persist_items: []
# - label: Google Chrome
#   path: /Applications/Google Chrome.app/
#   pos: 2
# - label: System Preferences
#   path: /System/Applications/System Preferences.app/
#   pos: 10
```

## Dependencies

- `rarango9.command_line_tools` (Work in Progress)
- `rarango9.homebrew` (Work in Progress)
- `community.general`

## Example Playbook

```yaml
- hosts: localhost

  vars:
    dock_autohide: yes

    dock_screen_position: bottom

    dock_remove_items:
      - Launchpad
      - Apple TV

    dock_persist_items:
      - label: Google Chrome
        path: /Applications/Google Chrome.app/
        pos: 2
      - label: System Preferences
        path: /System/Applications/System Preferences.app/
        pos: 10

  roles:
    - rarango9.dock
```

## License

MIT

## Author Information

Created by Rob Arango as part of the MacMods Ansible Collection.
