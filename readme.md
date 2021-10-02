# Pgtool

<!--- mdtoc: toc begin -->

1. [Prereqs](#prereqs)
2. [Usage](#usage)
3. [Config file layout](#config-file-layout)<!--- mdtoc: toc end -->

## Prereqs

1. [stoml](https://github.com/freshautomations/stoml) which is used to read config files

## Usage

```go mdox-exec="cat doc/help.txt"
Command and config required. Please provide both args.

Available commands:
    pull   - pull db and save to gz file, pgdump
    push   - use dump and push it into a database
    drop   - drop database
    create - create database

Usage:
    pgtool pull conf.toml
    pgtool push conf.toml dump.gz
    pgtool drop conf.toml
    pgtool create conf.toml
```

## Config file layout

Config files are written in toml and look like this.

```toml
pg_host = "postgres_host"
pg_port = "5432"
pg_db = "db_name"
pg_user = "user"
pg_pass = "password"
```
