# Ansible Role: Firewall

This role installs the security utility _Fail2Ban_ onto the server, configures the main application and its' jails according to the user-provided variables and makes sure to start the `fail2ban.service`. Furthermore the service is automatically enabled on the system so that it starts even after shutdown.

## Requirements

N/A

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
fail2ban_loglevel: INFO
fail2ban_logtarget: /var/log/fail2ban.log

fail2ban_ignoreself: "true"
fail2ban_ignoreips:
  - "127.0.0.1/8"
  - "::1"
  - "147.78.126.74"

# In seconds
fail2ban_bantime: 600
fail2ban_findtime: 600

fail2ban_maxretry: 5
fail2ban_destemail: root@localhost
fail2ban_sender: root@{{ ansible_fqdn }}

# JAIL configuration
fail2ban_sshd_enabled: true
fail2ban_sshd_port: 4322
fail2ban_sshd_log_path: /var/log/auth.log

fail2ban_apache_enabled: true
fail2ban_apache_ports:
  - 80
  - 443

fail2ban_traefik_enabled: true
fail2ban_traefik_ports:
  - 80
  - 443

fail2ban_wordpress_enabled: true
fail2ban_wordpress_ports:
  - 80
  - 443

fail2ban_grafana_enabled: true
fail2ban_grafana_ports:
  - 80
  - 443
```

## Dependencies

None.

## Example Playbook

```yaml
    - hosts: all
      roles:
        - role: fail2ban
```

## License

Proprietary

## Author Information

This role was created in 2023 by [Maximilian Gindorfer](https://fmj.dev).
