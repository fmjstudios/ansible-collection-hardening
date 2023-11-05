# Ansible Role: Firewall

This role configures the server's firewall via the `iptables` command-line client application. Futhermore it disables other firewall clients like `ufw` or `firewalld` and set's up an init-script for `starting/restarting/stopping/..` the firewall created via `iptables`.

## Requirements

N/A

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
firewall_state: started
firewall_enabled_at_boot: true
firewall_flush_rules_and_chains: true
firewall_allowed_tcp_ports: []
firewall_allowed_udp_ports: []
firewall_forwarded_tcp_ports: []
firewall_forwarded_udp_ports: []
firewall_additional_rules: []
firewall_enable_ipv6: true
firewall_ip6_additional_rules: []
firewall_log_dropped_packets: true

# Set to true to ensure other firewall management software is disabled.
firewall_disable_firewalld: false
firewall_disable_ufw: false
```

## Dependencies

None.

## Example Playbook

```yaml
    - hosts: all
      roles:
        - role: firewall
```

## License

Proprietary

## Author Information

This role was created in 2023 by [Maximilian Gindorfer](https://fmj.dev).
