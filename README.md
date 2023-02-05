# useful-docker-commands
List of useful docker commands

# SQL Server
docker run -d --name sql-container \
--network mydockernetwork \
--restart always \
-e ACCEPT_EULA=Y -e SA_PASSWORD=<your-password> -e MSSQL_PID=Express \
-p 1433:1433 mcr.microsoft.com/mssql/server:2017-latest-ubuntu 

# Mongo db
docker run -it -d --name mongo-container -p 27017:27017 \
--network mydockernetwork --restart always \
-v mongodb_data_container:/data/db mongo:latest

# PostgreSQL
docker run --name dev \
-e POSTGRES_USER=<your-username> -e POSTGRES_PASSWORD=<your-password> \
-p 5432:5432 -d postgres:latest
