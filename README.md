
williamyeh.mongodb_exporter for Ansible Galaxy
============

[![Circle CI](https://circleci.com/gh/William-Yeh/ansible-mongodb-exporter.svg?style=shield)](https://circleci.com/gh/William-Yeh/ansible-mongodb-exporter)



## Summary

Role name in Ansible Galaxy: **[williamyeh.mongodb_exporter](https://galaxy.ansible.com/detail#/role/4465)**

This Ansible role has the following features for [mongodb_exporter](https://github.com/dcu/mongodb_exporter) (a MongoDB metrics exporter for [Prometheus](http://prometheus.io/)):

 - Install a pre-compiled version of mongodb_exporter (I hope the maintainer of mongodb_exporter will provide official binary releases).
 - Handlers for restart/reload/stop events.




## Role Variables

### Mandatory variables

None.



### Optional variables


**Mongodb_exporter specific** user-configurable defaults:

```yaml
# MongoDB Connection String URI
# @see http://docs.mongodb.org/manual/reference/connection-string/
mongodb_exporter_mongodb_uri:  "mongodb://localhost:27017"
```


**Prometheus** user-configurable defaults (of course, a subset of optional variables in [williamyeh.prometheus](https://github.com/William-Yeh/ansible-prometheus)):

```yaml
# user and group
prometheus_user:   prometheus
prometheus_group:  prometheus


# directory for executable files
prometheus_install_path:   /opt/prometheus

# directory for logs
prometheus_log_path:       /var/log/prometheus

# directory for PID files
prometheus_pid_path:       /var/run/prometheus


# version of helper utility "gosu"
gosu_version:  1.7
```


## Handlers

- `restart mongodb_exporter`

- `reload mongodb_exporter`

- `stop mongodb_exporter`



## Usage


### Step 1: add role

Add role name `williamyeh.mongodb_exporter` to your playbook file.


### Step 2: add variables

Set vars in your playbook file, if necessary.

Simple example:

```yaml
---
# file: simple-playbook.yml

- hosts: all
  sudo: True
  roles:
    - williamyeh.mongodb_exporter

  vars:

    mongodb_exporter_mongodb_uri:  "mongodb://adm:password@localhost:27017"


```




## Dependencies

None.


## License

MIT License. See the [LICENSE file](LICENSE) for details.
