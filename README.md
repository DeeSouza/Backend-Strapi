# Strapi application

A quick description of your strapi application

### Create Image Docker Postgres

```sh
docker run -d \
 --name backend_strapi \
 -p 5432:5432 \
 -e POSTGRES_USER=strapi \
 -e POSTGRES_PASSWORD=strapi \
 -e POSTGRES_DB=strapi \
 postgres
```

### Start a Image Docker Container

```sh
docker start <container_name>
```

### Create a Strapi Project

```sh
yarn create strapi-app backend
```

### Restore Database

```sh
psql -h 127.0.0.1 -U postgres -d strapi -W < strapi.sql
```

**Docker**

```sh
docker exec -i pg_container_name psql --username pg_username [--password pg_password] database_name [-W ask password] < /path/on/your/machine/dump.sql
```

### Backup Database

```sh
pg_dump -c --if-exists --exclude-table=strapi_administrator -h 127.0.0.1 -U postgres -d strapi -W > strapi.sql
```

**Docker**

```sh
docker exec -i pg_container_name pg_dump --username pg_username [--password pg_password] database_name > /desired/path/on/your/machine/dump.sql
```
