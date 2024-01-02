# Start Local PostgreSQL

## When `docker-compose.yml` is ready and in the root folder i.e. inside PostgreSQL directory

```bash
docker-compose up
```
## When `docker-compose.yml` is in different directory i.e. nested folders, provide the path with -f option.

```bash
docker-compose -f ./PostgreSQL/docker-compose.yml up
```
