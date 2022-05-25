# Keepalived

An Ansible role that installs, configures and manages keepalived for EL 8.

This role will clone the keepalived source code from github.com, and install the application from source.

## Configuration
Set version to install with:

```yaml
keepalived_version: v2.2.7
```

Config file:
```yaml
keepalived_config: /etc/keepalived/keepalived.conf
```

Since the application is installed from source, the git repository is cloned to the following directory:

```yaml
keepalived_checkout_path: /var/lib/keepalived/
```

Set notification emails with:
```yaml
keepalived_global_defs:
  notification_email: []
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

## Requirements

Given all this, the minimum requirements are:

 * At least 2 hosts in play
 * Connection to the release file: https://github.com/acassen/keepalived.git
