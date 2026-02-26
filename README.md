# Ansible Role: netbird

Installs and configures the Netbird VPN client.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

### `netbird_version`

The version of Netbird to install (e.g., `"0.66.0"`). This is primarily used for binary installation, but can be informative for other methods.

### `netbird_state`

Controls whether the Netbird client is installed or uninstalled.
Default: `"present"`

**Note:** When set to `absent`, the Netbird client is uninstalled.

### `netbird_install_method`

The installation method is automatically detected based on the distribution.
- `deb`: For Debian/Ubuntu based systems.
- `rpm`: For RHEL/CentOS/Fedora based systems.
- `pacman`: For Arch Linux based systems.
- `binary`: For other Linux systems.

### `netbird_arch`

The architecture of the system. Automatically detected.

### `netbird_service_name`

The name of the systemd service.
Default: `"netbird"`

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: netbird
      vars:
        netbird_version: "0.66.0"
```

## License

MIT

## Author Information

This role was created by null-dev.
