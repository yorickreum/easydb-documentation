---
title: "eas.yml"
layout: config
menu:
  main:
    name: "eas.yml"
    identifier: "sysadmin/konfiguration/eas.yml"
    parent: "sysadmin/konfiguration"
    weight: 60
---

# eas.yml

This configuration is placed outside of the container, e.g. into `/srv/easydb/config/eas.yml`, assuming your base directory is `/srv/easydb`.

| variable | type | default | description |
|----------|------|---------|-------------|
|`canonical-name`          | `string` | `easydb-eas` | external name of EAS |
|`docker-hostname`         | `string` | `easydb-eas` | name of docker container |
|`log-level`               | one of `debug`, `info`, `warn`, `error` | `info` | log level |
|`pgsql`                   |          |              | connection settings for PostgreSQL |
|&#8193;`host`             | `string` | `easydb-pgsql` | |
|&#8193;`port`             | `integer` | `5432` | |
|&#8193;`username`         | `string` | `***` | |
|&#8193;`password`         | `string` | `***` | |
|&#8193;`database`         | `string` | `eas` | |
|`smtp`                    |          |       | mail server settings |
|&#8193;`server`           | `string` | `mail` | |
|&#8193;`from-address`     | `string` | `root@localhost` | |
|&#8193;`hostname`         | `string` | `localhost` | |
|`imagemagick`             |          | | ImageMagick settings |
|&#8193;`policy`           |          | | IM policies |
|&#8193;&#8193;`resource`  |          | | IM resource policies |
|&#8193;&#8193;&#8193;`memory` | `string` | `1024MiB` | |
|&#8193;&#8193;&#8193;`map`    | `string` | `2048MiB` | |
|&#8193;&#8193;&#8193;`width`  | `string` | `64KP` | |
|&#8193;&#8193;&#8193;`height` | `string` | `64KP` | |
|&#8193;&#8193;&#8193;`area`   | `string` | `512MB` | |
|&#8193;&#8193;&#8193;`disk`   | `string` | `4GiB` | |
|`apache-mmap`             | `string` | `"on"` | Alternative: `"off"`. Whether to use Apache's `EnableMMap`, see [here](/en/sysadmin/eas/faq#corrupted-asset-read-access). |
|`num-workers`             | `integer` | `1` | Maximum simultaneous processes of time-intensive work. Also see [here](/en/sysadmin/eas/conf/#number-of-workers). Should not be bigger than the number of CPU cores. |
|`num-soffice`             | `integer` | `2` | Maximum simultaneous processes of office documents. Must always be bigger than `num-workers`. |
|`num-services`             | `integer` | `5` | See [here](/en/sysadmin/eas/conf/#eas-num-services). |


## example

```yaml
canonical-name: https://official.example.com
log-level: debug
pgsql:
  host: pgsql
  port: 15432
  username: docker
  password: d8s2H3.mgy/ap6
  database: eas
num-workers: 4
num-soffice: 5
trusted-net: 10.123.123.0/24

smtp:
  server: relay.example.com
  hostname: easydb-server.example.com
  from-address: noreply@example.com
```

In many cases you do not need this file at all.

The typical `eas.yml` only contains `num-workers` and `num-soffice`.
