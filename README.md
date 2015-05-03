Ansible Role: Time
==================

This [Ansible](http://www.ansible.com/home) role configures the system time using ntp (network time protocol).

## Prerequisites

* None

## Platform support

* See [meta info](meta/main.yml)

## How to use

* Add a similar line to your Ansible playbook's role section as shown below:
```
roles:
    - { role: time, time_ntp_config_server_list: [ 'time1.mydomain.com', 'time2.mydomain.com' ] }
```
* Or with tags:
```
roles:
    - { role: time, time_ntp_config_server_list: [ 'time1.mydomain.com', 'time2.mydomain.com' ], tags: [ 'ntp', 'time' ] }
```

### Sample playbook

* site.yml:
```
  - hosts: servers
    vars_files:
      - vars/main.yml
    roles:
      - { role: time }
```
* vars/main.yml:
```
time_zoneinfo: Europe/Zurich
```

## Configuration

### Tags

The following Ansible tags allow to run this role more granular.

| Tag | Description |
|-----|-------------|
| config | Applies all the configuration and restarts affected services to make sure the new config is being loaded |
| service | Enables the required service(s) |
| package | Makes sure required packages are installed |
| ntp | Runs everything related to the ntp setup and config |
| timezone | Runs everything related to the timezone setup and config |

### Variables

See [defaults](defaults/main.yml).
