# Concept Quest - Database (PostgreSQL)

This container runs PostgreSQL for the Concept Quest platform.

## Connection info

The template writes a connection helper file:

- `core_database/db_connection.txt`

Example contents:

```
psql postgresql://appuser:dbuser123@localhost:5000/myapp
```

The backend expects (recommended) env var:

- `POSTGRES_URL=postgresql://appuser:dbuser123@localhost:5000/myapp`

## Schema / tables

For preview simplicity, the **backend creates tables automatically** at startup using SQLAlchemy `create_all` and inserts minimal seed data (games, levels, achievements, syllabus mappings).

This avoids migrations complexity while still enabling an end-to-end vertical slice.

## Notes

- Port `5000` is Postgres.
- Port `5001` is used by the DB visualizer service in this template.
