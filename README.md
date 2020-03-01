# Docker Compose for Devs #

Docker compose file with common services used by Devs on local environment  

### Services ###

* Postgres;
* PG Admin;
* RabbitMQ;
* ActiveMQ;
* DynamoDB:
* Elastic Search: *30 days trial licence*;
* Kibana: *30 days trial licence*;

### Prerequisite ###

1. Installing Docker:
https://docs.docker.com/install/linux/docker-ce/ubuntu/

2. Installing docker-compose:
https://docs.docker.com/compose/install/

### Accessing using Browser ###

- Postgres JDBC (using exposed postgres container port: *15432*):

```jdbc:postgresql://localhost:15432/postgres```

- PG Admin (login: *admin*| password: *admin* | Using external container port: *15433*): http://localhost:15433

- RabbitMQ (login: *guest*| password: *guest*): http://localhost:15672

- ActiveMQ (login: *admin*| password: *admin*): http://localhost:8161/admin/

- DinamoDB (*no credentials required*): http://localhost:4569/

*Important: Connection with postgres running in docker use postgres container name `postgres` as host name and internal container port `5432`:*

```
Host name/address: postgres
Port: 5432
Maintenance database: postgres 
Username: admin
Password: admin
```

### Postgres and PG Admin ###

- Use PG Admin to backup and restore dbs using a visual interface;
- To create a connection on PG Admin to access Postgres running in docker container, follow the final part o this article (portuguese):
```
https://medium.com/@renato.groffe/postgresql-docker-executando-uma-inst%C3%A2ncia-e-o-pgadmin-4-a-partir-de-containers-ad783e85b1a4
```  

### How to use ###

On terminal, go to `docker-compose-for-devs` folder and run the commands bellow: 
 

* Installing *all images* and starting containers:
```
docker-compose up -d
```

* Starting containers *with existing data*:
```
docker-compose start
```

* Stopping containers *keeping current data*:
```
docker-compose stop
```
 
* Stopping and removing containers (*all data will be lost*):
```
docker-compose down
```
