# Pgtool

<!--- mdtoc: toc begin -->

1. [Prereqs](#prereqs)
2. [Usage](#usage)
3. [Config file layout](#config-file-layout)<!--- mdtoc: toc end -->

## Prereqs

Required are `pg_dump`, `psql`, `createdb`, `dropdb`.

```shell
# install on ubuntu
apt install -u postgresql-client
```

## Usage

```go mdox-exec="cat doc/help.txt"
Command and config required. Please provide both args.

Available commands:
    pull   - pull db and save to gz file, pgdump
    push   - use dump and push it into a database
    drop   - drop database
    list   - list tables

Usage:
    pgtool pull conf.toml
    pgtool push conf.toml dump.gz
    pgtool drop conf.toml
    pgtool list conf.toml
```

## Config file layout

Config files are written in toml and look like this. Commented values will not be passed to final run commands.

```toml
pg_host = "postgres_host"
pg_port = "5432"
pg_db = "db_name"
pg_user = "user"
# pg_pass = "password"
```
