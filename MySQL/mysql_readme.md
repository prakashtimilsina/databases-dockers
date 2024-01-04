# Start Local MySQL

## When `docker-compose.yml` is ready and in the root folder i.e. inside MySQL directory

```bash
docker-compose up
```
## When `docker-compose.yml` is in different directory i.e. nested folders, provide the path with -f option.

```bash
docker-compose -f ./MySQL/docker-compose.yml up
```

# Access Adminer
- Go to `http://localhost:8080` to access Adminer portal.
- Enter respective credentials after selecting system as `MySQL` and click login
- You are connected to mysql GUI and good to go now!

# Run Commands inside the container
## Run the below commands and click enter to know version of the MySQL.

```bash
docker-compose -f ./MySQL/docker-compose.yml run db mysql -U prakashtcoder -p --host db"
```
# Access MySQL Monitor

- `-f ./MySQL/docker-compose.yml` : points to the file where to run docker compose on. If we have `docker-compose.yml` in same folder, we do not need to pass this option.
- `run db` : runs a one-time command in the `db` service defined in the Docker Compose file.
- `mysql` : initiates the MySQL command-line client.
-  `-U prakashcoder` : specifies the mysql username as `prakashcoder`
- `-p ` Prompts for the MySQL user's password. **This flag indicates that the user's password will be entered interactively after running the command.**
- `--host db` : Specifies the host where the MySQL server is running. In this case, it's set to `db`, which is likely the name of the service defined in the `docker-compose.yml` file.
- `-d prakashdb` : Specifies the name of the postgresql database as `prakashdb`
- `-c "SELECT version();"`: exectutes the SQL query `SELECT version();` over the database.

Running this command will prompt you to enter the password. Enter `MYSQL_PASSWORD` env variable value from the docker compose file.

After successful execution of command, you can run the mysql related commands here.

# List all the databases
Run the below command to display all the databases.
```bash
show databases;
```