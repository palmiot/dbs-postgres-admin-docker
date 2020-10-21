# dbs-postgres-admin-docker

This is a little and portable ecosystem for store or manage PostgreSQL databases using docker-compose.


## Usage

Firstly you need made a copy of the next files for customize later as your preferences:

- `.env.example` to `.env`.
- `conf/postgres.conf.example` to `conf/postgres.conf`.
- create an empty folder named `sql` into `databases` as this `databases/sql`.

Using `docker-compose` becouse it's easy implement all.

```
$ cd /path-to-this-cloned-repo/dbs-postgres-admin-docker
$ docker-compose up -d
```

NOTE :: You can remove the argument `-d` if you want see the logs output of containers.

If you want remove all implement, you can use the next command;

```
$ docker-compose down
```

## The panel

Once running the containers, you can see the admin panel using any browser. For this you need know the host and type with correct port into your browser. Example;

```
http://172.20.0.6:8080 ( Adminer panel for manage the databases)

```

or

```
http://localhost:30080 ( The same Adminer panel )
```

The ip (or host) and port can be define into `.env` file for both services.


## Customize

You can set customized options into the file `.env` and optional configurations for services into `./conf/` directory. For first, you can follow the next table for understand the fields;


### Environment variables summary for `.env` file.

| Variables | description | default |
| ------------- | ------------- | ------------- |
| DBS_NAME | (string) Name of implementation, is irrelevant. | dbs-postgres-admin |
| DBS_NETWORK | (net) Configure a default network. | 172.20.0.0/24 |
| DBS_SHARED_SQL | (path) Directory of SQL storage. | ./databases/sql |
| DBS_SERVERS_SQL_IMAGE | (image:tag) Docker of SQL server. | postgres:latest |
| DBS_SERVERS_SQL_IP | (string ip) IP of PostgreSQL service. | 172.20.0.5 |
| DBS_SERVERS_SQL_PORT | (integer) Port of endpoint access. | 35432 |
| DBS_SERVERS_SQL_ROOT_PASSWORD | (string) The password for root user (postgres). | postgres |
| DBS_PANELS_SQL_IMAGE | (image:tag) Docker of Adminer. | adminer:latest |
| DBS_PANELS_SQL_PLUGINS | (string) List of public plugins. | '' |
| DBS_PANELS_SQL_DESIGN | (string) Name of the design for Adminer. | konya |
| DBS_PANELS_SQL_IP | (string ip) IP of Adminer panel. | 172.20.0.6 |
| DBS_PANELS_SQL_PORT | (integer) Port of endpoint access. | 30080 |


### File into the directory `./conf/*`

Means a basic implement of attributes into `postgres.conf` configuration file. You can add your rules into this file.
