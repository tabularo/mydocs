# Postgres

Setting up a PostGres demo DB

<br>

)

```{code-block} PostgreSQL
:caption: PostgreSQL Query

DO
$$
DECLARE
    _dbname text = 'airbnb';
    _exists bool;
BEGIN
    -- Check if the database already exists
    SELECT INTO _exists
    (SELECT 1 FROM pg_catalog.pg_database WHERE datname = _dbname);

    -- If the database does not exist, create it
    IF NOT _exists THEN
        EXECUTE 'CREATE DATABASE ' || _dbname;
    END IF;
END
$$;
```

For the code block creations/checking of schema and role can be performed using the DO block, but for the creation of the database, you have to check manually if the database exists and then create it, as PostgreSQL won't allow the CREATE DATABASE inside a transaction block.

```{code-block} PostgreSQL
:caption: PostgreSQL Query

-- Create the role
DO $$
BEGIN
   IF NOT EXISTS (
      SELECT FROM pg_catalog.pg_roles WHERE rolname = 'transform')
   THEN
      CREATE ROLE transform;
   END IF;
END
$$;

-- Create a user and assign it to the role
DO $$
BEGIN
   IF NOT EXISTS (
      SELECT FROM pg_catalog.pg_roles WHERE rolname = 'dbt')
   THEN
      CREATE USER dbt PASSWORD 'dbtPassword123' IN ROLE transform;
   END IF;
END
$$;
```

Run this after you've created and switched to the airbnb database:

```{code-block} PostgreSQL
:caption: PostgreSQL Query
-- Create a schema
DO $$
BEGIN
   IF NOT EXISTS (
      SELECT schema_name FROM information_schema.schemata WHERE schema_name = 'raw')
   THEN
      CREATE SCHEMA raw;
   END IF;
END
$$;

-- Grant all privileges to the role
GRANT ALL PRIVILEGES ON SCHEMA raw TO transform;
ALTER DEFAULT PRIVILEGES IN SCHEMA raw GRANT ALL ON TABLES TO transform;
```

Create tables for demo db

```{code-block} sql
:caption: PostgreSQL Query

-- Create tables
CREATE TABLE IF NOT EXISTS raw_listings
(
    id integer,
    listing_url text,
    name text,
    room_type text,
    minimum_nights integer,
    host_id integer,
    price text,
    created_at timestamp,
    updated_at timestamp
);

CREATE TABLE IF NOT EXISTS raw_reviews
(
    listing_id integer,
    date timestamp,
    reviewer_name text,
    comments text,
    sentiment text
);

CREATE TABLE IF NOT EXISTS raw_hosts
(
    id integer,
    name text,
    is_superhost text,
    created_at timestamp,
    updated_at timestamp
);
```
