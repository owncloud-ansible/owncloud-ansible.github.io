---
title: "Redis"
date: 2019-03-26T08:47:11+01:00
---

> **WARNING**: This Ansible role is currently in beta state. Use it at your own risk.


Ansible role to setup Redis server

## Table of content

* [Default Variables](#default-variables)
  * [redis_appendfsync](#redis_appendfsync)
  * [redis_appendonly](#redis_appendonly)
  * [redis_bind_interface](#redis_bind_interface)
  * [redis_databases](#redis_databases)
  * [redis_dbdir](#redis_dbdir)
  * [redis_dbfilename](#redis_dbfilename)
  * [redis_disabled_commands](#redis_disabled_commands)
  * [redis_includes](#redis_includes)
  * [redis_logfile](#redis_logfile)
  * [redis_loglevel](#redis_loglevel)
  * [redis_maxmemory](#redis_maxmemory)
  * [redis_maxmemory_policy](#redis_maxmemory_policy)
  * [redis_maxmemory_samples](#redis_maxmemory_samples)
  * [redis_packages](#redis_packages)
  * [redis_packages_extra](#redis_packages_extra)
  * [redis_port](#redis_port)
  * [redis_rdbcompression](#redis_rdbcompression)
  * [redis_requirepass](#redis_requirepass)
  * [redis_save](#redis_save)
  * [redis_timeout](#redis_timeout)
  * [redis_unixsocket](#redis_unixsocket)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### redis_appendfsync

#### Default value

```YAML
redis_appendfsync: everysec
```

### redis_appendonly

#### Default value

```YAML
redis_appendonly: no
```

### redis_bind_interface

#### Default value

```YAML
redis_bind_interface: 127.0.0.1
```

### redis_databases

#### Default value

```YAML
redis_databases: 16
```

### redis_dbdir

#### Default value

```YAML
redis_dbdir: /var/lib/redis
```

### redis_dbfilename

#### Default value

```YAML
redis_dbfilename: dump.rdb
```

### redis_disabled_commands

Disable certain Redis commands for security reasons.

#### Default value

```YAML
redis_disabled_commands: []
```

#### Example usage

```YAML
redis_disabled_commands:
  - FLUSHDB
  - FLUSHALL
  - KEYS
  - PEXPIRE
  - DEL
  - CONFIG
  - SHUTDOWN
  - BGREWRITEAOF
  - BGSAVE
  - SAVE
  - SPOP
  - SREM
  - RENAME
  - DEBUG
```

### redis_includes

Add extra include files for local configuration/overrides.

#### Default value

```YAML
redis_includes: []
```

### redis_logfile

#### Default value

```YAML
redis_logfile: /var/log/redis/redis-server.log
```

### redis_loglevel

#### Default value

```YAML
redis_loglevel: notice
```

### redis_maxmemory

#### Default value

```YAML
redis_maxmemory: 0
```

### redis_maxmemory_policy

#### Default value

```YAML
redis_maxmemory_policy: noeviction
```

### redis_maxmemory_samples

#### Default value

```YAML
redis_maxmemory_samples: 5
```

### redis_packages

Define a custom list of packages to install. Default value depends on your operating system.

#### Default value

```YAML
redis_packages: _os_specific_
```

### redis_packages_extra

Can be used to install other dependency packages.

#### Default value

```YAML
redis_packages_extra: []
```

### redis_port

#### Default value

```YAML
redis_port: 6379
```

### redis_rdbcompression

#### Default value

```YAML
redis_rdbcompression: yes
```

### redis_requirepass

Require authentication to Redis with a password.

#### Default value

```YAML
redis_requirepass: _unset_
```

### redis_save

Set to an empty set to disable persistence (saving the DB to disk).

#### Default value

```YAML
redis_save:
  - 900 1
  - 300 10
  - 60 10000
```

### redis_timeout

#### Default value

```YAML
redis_timeout: 300
```

### redis_unixsocket

#### Default value

```YAML
redis_unixsocket: _unset_
```

## Dependencies

None.
