# Ansible Role: systemd_timesyncd

## Description

Manage systemd-timesyncd - Network Time Synchronization service.

## Requirements

None

## Dependencies

None

## OS Platforms

- AlmaLinux8 or higher
- Rockylinux8 or higher
- Ubuntu-20.04 or higher

## Example Playbook

```
- hosts: all
  roles:
    - systemd_timesyncd
```

## Role Variables

### systemd_timesyncd_package_ensure: (string)

```
systemd_timesyncd_package_ensure: 'present'
```

### systemd_timesyncd_service_ensure: (string)

```
systemd_timesyncd_service_ensure: 'started'
```

### systemd_timesyncd_service_enable: (bool)

```
systemd_timesyncd_service_enable: true
```

### systemd_timesyncd_config_options: (dict)

```
systemd_timesyncd_config_options: {}
```

### systemd_timesyncd_dropin_config_options: (dict)

```
systemd_timesyncd_dropin_config_options: {}
```

## Example vars

```
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

