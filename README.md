  # - aaaa@example.com
  # - bbbb@example.com
  # - cccc@example.com
  notification_email_from: ""
  smtp_server: ""
  smtp_connect_timeout: 10
```

Interface to attach to:

```yaml
keepalived_interface: eth0
keepalived_system_ip: "{{ ansible_default_ipv4.address }}"
```

If you want to specify a certain script:
```yaml
keepalived_script:
  name: something
  script: /usr/bin/pgrep service-name
  interval: 2
```

Set the roles and IP's:
```yaml
keepalived_role: MASTER  # or BACKUP
keepalived_vip: 10.0.0.5
```

# Requirements

Given all this, the minimum requirements are:

 * At least 2 hosts in play
 * Connection to the release file: https://github.com/acassen/keepalived.git
