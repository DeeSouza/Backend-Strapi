# Strapi application

A quick description of your strapi application

### Create Image Docker Postgres

```sh
docker run --name backend_strapi -e POSTGRES_PASSWORD=strapi -p 5432:5432 -d postgres
```

### Create a Strapi Project

```sh
yarn create strapi-app backend
```

### Restore Database

```sh
psql -h 127.0.0.1 -U postgres -d strapi -W < strapi.sql 
```

### Backup Database

```sh
pg_dump -c --if-exists --exclude-table=strapi_administrator -h 127.0.0.1 -U postgres -d strapi -W > strapi.sql
```
