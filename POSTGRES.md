# Postgres Instructions

## Getting a database dump

Use `pg_dump` in "schema-only" mode:

```
pg_dump --dbname=$dbname --host=$host --port=$port --no-owner --no-privileges --schema-only --no-security-labels
```

Write to a file named `schema.sql`.

## Recompile the datamodels

You'll need Postgres installed locally with `psql` in your `$PATH` and the [prisma-render](https://github.com/prisma/prisma-render) CLI in your `$PATH`.

Then run:

```sh
git clone https://github.com/prisma/database-schema-examples
cd database-schema-examples
make
```

If you don't have Postgres installed locally or you want to load these schemas into a remote Postgres instance, you can use the environment variable PG_URL=postgres://<remote-url>

```sh
PG_URL=postgres://... make
```

