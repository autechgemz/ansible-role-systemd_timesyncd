# Ansible Role: systemd_timesyncd

## Description

Manage systemd-timesyncd - Network Time Synchronization service.

## Requirements

- Ansible >= 2.9

## Dependencies

- EPEL repository (RedHat family only)

## OS Platforms

- AlmaLinux8+
- Rockylinux8+
- CentOS8+
- Ubuntu-20.04+

## Example Playbook

```yaml
- hosts: all
  roles:
    - systemd_timesyncd
```

## Role Variables

### systemd_timesyncd_package_ensure: (string)

```yaml
systemd_timesyncd_package_ensure: 'present'
```

### systemd_timesyncd_service_ensure: (string)

```yaml
systemd_timesyncd_service_ensure: 'started'
```

### systemd_timesyncd_service_enable: (bool)

```yaml
systemd_timesyncd_service_enable: true
```

### systemd_timesyncd_config_options: (dict)

```yaml
systemd_timesyncd_config_options: {}
```

### systemd_timesyncd_dropin_config_options: (dict)

```yaml
systemd_timesyncd_dropin_config_options: {}
```

## Example vars

```yaml
systemd_timesyncd_config_options:
  NTP:
    - 'time1.google.com'
    - 'time2.google.com'
    - 'time3.google.com'
    - 'time4.google.com'
  RootDistanceMaxSec: 5
  PollIntervalMinSec: 32
  PollIntervalMaxSec: 2048

systemd_timesyncd_dropin_config_options:
  - name: fallback_ntp.conf
    content:
      FallbackNTP:
        - 0.ubuntu.pool.ntp.org
        - 1.ubuntu.pool.ntp.org
        - 2.ubuntu.pool.ntp.org
        - 3.ubuntu.pool.ntp.org
```
