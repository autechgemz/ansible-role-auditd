# Ansible Role: auditd

## Description

Manage Security Auditing Service. 

## Requirements

None

## Dependencies

None

## OS Platforms

- Ubuntu-20 or higher

## Example Playbook

```
- hosts: all
  roles:
    - auditd
```

## Role Variables

### auditd_package_ensure: (string)

```
auditd_package_ensure: 'present'
```

### auditd_service_ensure: (string)

```
auditd_service_ensure: 'started'
```

### auditd_service_enable: (bool)

```
auditd_service_enable: true
```

### auditd_daemon_config_options: (dict)

```
auditd_daemon_config_options: None
```

### auditd_config_options: (dict)

```
auditd_config_options: None
```

### auditd_rules_options: (list)

```
auditd_rules_options: None
```

## Example vars

```
auditd_rules_options:
  - '-w /etc/passwd -p wa -k passwd_changes'
  - '-a exit,never -F dir=/dev -k exclude'
  - '-a exit,never -F dir=/proc -k exclude'
  - '-a exit,never -F dir=/sys -k exclude'
  - '-a exit,never -F dir=/tmp -k exclude'
  - '-a exit,never -F dir=/var -k exclude'
  - '-a exit,always -F dir=/ -F perm=wa -k file_changes'
  - '-e 2'
```
