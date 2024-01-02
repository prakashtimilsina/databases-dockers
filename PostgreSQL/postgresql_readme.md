# Start Local PostgreSQL

## When `docker-compose.yml` is ready and in the root folder i.e. inside PostgreSQL directory

```bash
docker-compose up
```
## When `docker-compose.yml` is in different directory i.e. nested folders, provide the path with -f option.

```bash
docker-compose -f ./PostgreSQL/docker-compose.yml up
```

# Access Adminer
- Go to `http://localhost:8080` to access Adminer portal.
- Enter respective credentials after selecting system as `PostgreSQL` and click login
- You are connected to postgresql GUI and good to go now!
