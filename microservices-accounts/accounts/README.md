**Set-up for local**

1. Recommended - 1 database for 1 microservice.
2. Execute:
   docker run -p 3306:3306 --name accountsdb -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=accountsdb -d mysql
- e = environment variable
- MYSQL_DATABASE = name of db to be created after image starts
2. Create connection (DB Navigator or other tool)
3. Add mysql-connector-j dependency to MS pom.xml
4. MS application.yml -> provide MySQL properties + sql: init: mode: always (to run sql scripts automatically)
5. Run db containers, run config-server, run ms

Set-up for container environment

1. docker-compose.yml -> create new services (db) + add db connection env var. to ms services
2. create new images of ms and config-server