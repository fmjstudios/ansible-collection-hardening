# Ansible Role: Maldet

This role configures Linux Malware Detect for the server.

## Requirements

N/A

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
download_dir: /tmp/downloads/maldet
cron_job_minute: 0
cron_job_hour: 12
cron_job_command: /usr/local/maldetect/maldet -b -r /home?/?/public_html/,/var/www/html/,/usr/local/apache/htdocs/ 1 >> /dev/null 2>&1

```

## Dependencies

None.

## Example Playbook

```yaml
    - hosts: all
      roles:
        - role: maldet
```

## License

Proprietary

## Author Information

This role was created in 2023 by [Maximilian Gindorfer](https://fmj.dev).
