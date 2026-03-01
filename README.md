# Ansible Role: netbird_client

Installs and configures the Netbird VPN client.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

### `netbird_version`

The version of Netbird to install (e.g., `"0.66.0"`). This is *only* applicable for `binary` installations and must be undefined or empty for all other methods (`deb`, `rpm`, `pacman`).

### `netbird_state`

Controls whether the Netbird client is installed or uninstalled.
Default: `"latest"`

**Note:** When set to `absent`, the Netbird client is uninstalled.

### `netbird_install_method`

The installation method is automatically detected based on the distribution.
- `deb`: For Debian/Ubuntu based systems: Installs netbird from the netbird APT repo.
- `rpm`: For RHEL/CentOS/Fedora based systems: Installs netbird from the netbird YUM repo.
- `pacman`: For Arch Linux based systems: Installs the [netbird-bin](https://aur.archlinux.org/packages/netbird-bin) package from the AUR.
- `binary`: For other Linux systems: Directly installs the netbird binary.

### `netbird_binary_install_dir`

The directory where the Netbird binary is installed for binary installations (Arch/Other).
Default: `"/usr/bin"`

### `netbird_arch`

The architecture of the system. Automatically detected.

### `netbird_service_name`

The name of the systemd service.
Default: `"netbird"`

## Dependencies

- `community.general`

## Example Playbook

```yaml
- hosts: all
  roles:
    - role: netbird_client
```

## License

MIT
