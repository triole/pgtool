# Pgtool

<!-- toc -->

- [Prereqs](#prereqs)
- [Usage](#usage)

<!-- /toc -->

## Prereqs

Required are `pg_dump`, `psql`, `createdb`, `dropdb`.

```shell
# install on ubuntu
apt install -u postgresql-client
```

## Usage

```go mdox-exec="cat doc/help.txt"
Command and config required. Please provide both args.

available commands
  pull   - pull db and save to gz file, pgdump
  push   - use dump and push it into a database
  drop   - drop database
  list   - list tables

flags
  -n/--dryrun   just print, don't do
  -v/--verbose  print every command before running it

usage
  pgtool pull conf.toml
  pgtool push conf.toml dump.gz
  pgtool drop conf.toml
  pgtool list conf.toml
```

## Config file layout

Config files are written in toml and look like this. Commented values will not be passed to final run commands.

```go mdox-exec="cat doc/conf.toml"
pg_host = "postgres_host"
pg_port = "5432"
pg_db = "db_name"
pg_user = "user"
# if password is disabled, like below, you'll be prompted
# pg_pass = "password"

# folder where to save the dumps, if not defined current dir
dump_dir = "/tmp"
```
