# PostgresSQL Docker Sandbox

# Features
 - [Postgres](https://www.postgresql.org/) sandbox database
 - [PGAdmin](https://www.pgadmin.org/) auto connected to postgres
 - [Schemaspy](https://schemaspy.org/) Analysis

# Sandbox database & PGAdmin
## Start services
```shell
$ docker-compose -f docker-compose.yaml up
```

## Run scripts on database
Store your `.sql` scripts in `/scripts` folder
```
# Run psql in your postgres containter
$ docker exec -it pgsandbox_postgres psql -U postgres
psql (14.5 (Debian 14.5-1.pgdg110+1))
Type "help" for help.

postgres=# \c sandbox
sandbox=# \i scripts/myscript.sql
```

## Access PGADMIN
Access PGAdmin interface on http://127.0.0.1:5050

# Run Schemaspy analysis
Update `schemaspy/config/schemaspy.properties` if required (eg update schema name)

Run schemaspy on your database:
```shell
$ docker-compose -f schemaspy.yaml up
```

Find the output in `/schemaspy/output/` (open index.html in your browser)


