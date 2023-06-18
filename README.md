# Introduction

Ansible module to deploy a redis replication cluster

# Usage

```yaml
---
- hosts: redis
  become: yes
  remote_user: julien
  vars:
  roles:
      - ansible-role-redisrepl
```

Mandatory variables :

# Run playbook

- default : deploy configuration


# Configuration :

| variable | role | default value |
|---|---|---|
| redis_config_redis_port | Define Redis Server port | 6379 |
| redis_config_appendonly | Enable/Disable AOF | yes |
| redis_config_appendfile | AOF Filename | appendonly.aof |
| redis_config_appendfsync | AOF Fsync mode | everysec |
| redis_config_save | Snapshots every x_seconds n_keys | 900 1\\300 10\\60 10000 |
| redis_config_requirepass | requirepass password, used for masterauth too (to set in your vault) | none (mandatory to define) |
| redis_config_slaves | list of servers from inventory used for replicaof configuration | none |
| redis_config_replicaof | master server name | none |


