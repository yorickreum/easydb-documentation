---
title: "9 - Operations"
menu:
  main:
    name: "Operations"
    identifier: "sysadmin/betrieb"
    parent: "sysadmin"
    weight: 7
---
# Operation

# Update

To **update** the easydb software, repeat the "[load easydb on the server](../installation)"  section of the installation:

```bash
docker pull docker.easydb.de/pf/server-$SOLUTION
docker pull docker.easydb.de/pf/webfrontend
docker pull docker.easydb.de/pf/elasticsearch
docker pull docker.easydb.de/pf/eas
docker pull docker.easydb.de/pf/postgresql
docker pull docker.easydb.de/pf/fylr
```

However, the downloaded version will not be used until the containers have been recreated.

# Stop and Recreate Containers

To **stop** the easydb and remove the current containers, use the following commands:

```bash
docker stop  easydb-webfrontend
docker rm -v easydb-webfrontend

docker stop  easydb-server
docker rm -v easydb-server

docker stop  easydb-fylr
docker rm -v easydb-fylr

docker stop  easydb-eas
docker rm -v easydb-eas

docker stop  easydb-elasticsearch
docker rm -v easydb-elasticsearch

docker stop  easydb-pgsql
docker rm -v easydb-pgsql
```

If you are running more than one easydb on a server, please note the additions in chapter [instantiation](/en/sysadmin/installation/instances/#instances).

&nbsp;

The easydb **start** commands are listed in the "[Start](../installation)" section of the installation. There, the containers will be recreated.

&nbsp;

# Status

Which easydb components are currently running can be displayed with `docker ps`. Here is a sample display while all components are running:

```bash
CONTAINER ID        IMAGE                                       COMMAND             CREATED             STATUS              PORTS                   NAMES
efe480718a0e        docker.easydb.de/pf/webfrontend        "/startup.sh"       9 days ago          Up 9 days           0.0.0.0:80->80/tcp      easydb-webfrontend
cdfe24889c0c        docker.easydb.de/pf/server-base        "/startup.sh"       9 days ago          Up 9 days           80/tcp, 3451-3452/tcp   easydb-server
2a77e387f88a        docker.easydb.de/pf/fylr               "/startup.sh"       2 days ago          Up 2 days           4000/tcp                easydb-fylr
8a17a2a5ea26        docker.easydb.de/pf/eas                "/startup.sh"       10 weeks ago        Up 10 weeks         80/tcp                  easydb-eas
19bf53e50287        docker.easydb.de/pf/elasticsearch      "/startup.sh"       10 weeks ago        Up 10 weeks         9200/tcp, 9300/tcp      easydb-elasticsearch
1a51017ae36e        docker.easydb.de/pf/postgresql         "/startup.sh"       10 weeks ago        Up 10 weeks         5432/tcp                easydb-pgsql
```

To display dormant components, use `docker ps -a`.

&nbsp;

## Monitoring

You can use our free [plugin](https://github.com/programmfabrik/check-easydb5) which works with either Nagios or Icinga, to monitor your easydb.

# Backup copies

## Securing the assets
Back up the directory that you specified for the data store during the [installation](../installation).

This means you have saved everything, including your assets.

But the information about the assets needs special care - they are stored in PostgreSQL databases, which could also change during backup.

## Backup the databases

The easydb internally uses two PostgreSQL databases. To copy them consistently, you have two options:

_Either - very simple:_

__A.__ Stop the easydb while backing up the data store.

_Or - our recommendation:_

__B.__ Use the PostgreSQL-specific tool `pg_dump`.

Pg_dump saves in a format which is still compatible after software updates.

The space requirement is also lower than with method A - if you exclude `pgsql/var` while saving the data storage.

## Backup using pg_dump

```bash
DATABASE=easydb5

docker exec easydb-pgsql pg_dump -U postgres -v -Fc -f /backup/$DATABASE.pgdump $DATABASE

docker exec easydb-pgsql pg_dump -U postgres -v -Fc -f /backup/eas.pgdump eas
```

Remarks:

- The easydb can and should run during this backup method. At least the component "easydb-pgsql" has to run.
- You will then find the backup files in the subdirectory `pgsql/backup/` of the data store defined during the [installation](../installation).
- If you first run pg_dump and then backup the data store, then you also include the dump files automatically.
- To display the database names you use, use the following:

```bash
docker exec easydb-pgsql psql -U postgres -l
```

They are typically eas and easydb5 (or eas and easydb).

&nbsp;

## maintenance contract

If you have a maintenance contract with us, we will let the linux host make dumps of the databases each night.

You can choose how many of them will be kept and at which time they are made. By default 7 dumps (one week) will be kept and the dump will be made each night at a time specified in a cron job file inside the directory `/etc/cron.d/`.

The dumps will be placed in the subdirectory `pgsql/backup/` of the data store defined during the [installation](../installation) (default: `/srv/easydb/`.

&nbsp;

# Restore a backup copy

1. Exit the easydb. (Described [top](#Operation) on this page)

2. Replace the contents of the data store with the backup copy. You have defined the data store at the [installation](../installation).

3. Start the first part of easydb - the component "easydb-pgsql". This is the first start command in the section "[Start](../installation)" of the installation.

4. If available, use the backup created by pg_dump:

```bash
DATABASE=easydb5
docker exec -i -t easydb-pgsql psql -U postgres -c 'DROP   DATABASE "eas"'
docker exec -i -t easydb-pgsql psql -U postgres -c 'DROP   DATABASE "'$DATABASE'"'
docker exec -i -t easydb-pgsql psql -U postgres -c 'CREATE DATABASE "eas"'
docker exec -i -t easydb-pgsql psql -U postgres -c 'CREATE DATABASE "'$DATABASE'"'
docker exec -i -t easydb-pgsql pg_restore -U postgres -v -d eas    /backup/eas.pgdump
docker exec -i -t easydb-pgsql pg_restore -U postgres -v -d $DATABASE /backup/$DATABASE.pgdump
```

5. Now start the remaining components. To do this, use the remaining start commands in the [Start](../installation) section.

Remarks:

- To display the database names you use, use the following:

```bash
docker exec -i -t easydb-pgsql psql -U postgres -l
```

They are typically eas and easydb5 (or eas and easydb).

&nbsp;
