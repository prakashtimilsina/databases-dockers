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

# Run Commands inside the container
## Run the below commands and click enter to know version of the PostgreSQL.

```bash
docker-compose -f ./PostgreSQL/docker-compose.yml run db psql -U prakashtcoder -p 5432 -h db -d prakashdb -c "SELECT version();"
```
- `-f ./PostgreSQL/docker-compose.yml` : points to the file where to run docker compose on. If we have `docker-compose.yml` in same folder, we do not need to pass this option.
- `run db` : runs a one-time command in the `db` service defined in the Docker Compose file.
- `psql` : initiates the PostgreSQL command-line client.
-  `-U prakashcoder` : specifies the postgresql username as `prakashcoder`
- `-p 5432` : Specifies the port number (5432) on which the PostgreSQL server is running. If the port is `5432` then this flag is optional.
- `-h db` : Specifies the host as `db` where the PostgreSQL server is located.
- `-d prakashdb` : Specifies the name of the postgresql database as `prakashdb`
- `-c "SELECT version();"`: exectutes the SQL query `SELECT version();` over the database.

Running this command will prompt you to enter the password. Enter `POSTGRES_PASSWORD` env variable value from the docker compose file. 

After successful execution of command, you can run the posegresql related commands here.
