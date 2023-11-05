# Ansible Role: ClamAV

This role configures the ClamAV antivirus daemon for the server.

## Requirements

N/A

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
clamav_daemon_configuration_changes:
  - regexp: "^.*Example$"
    state: absent
  - regexp: "^.*LocalSocket .*$"
    line: "LocalSocket {{ clamav_daemon_localsocket }}"

# clamav_daemon: 'clamav-daemon'
clamav_daemon_state: started
clamav_daemon_enabled: true

# clamav_freshclam_daemon: 'clamav-freshclam'
clamav_freshclam_daemon_state: started
clamav_freshclam_daemon_enabled: true
```

## Dependencies

None.

## Example Playbook

```yaml
    - hosts: all
      roles:
        - role: clamav
```

## License

Proprietary

## Author Information

This role was created in 2023 by [Maximilian Gindorfer](https://fmj.dev).
