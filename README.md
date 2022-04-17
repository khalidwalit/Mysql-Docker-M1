# Mysql-Docker-M1

How to run MySQL in Docker using the M1 silicon chip, for noobies

Pull mysql images for m1 architecture.

$ docker pull mysql/mysql-server:latest-aarch64

Note: mysql-server:latest-aarch64 changes the architecture so it will be compatible, and readable for your M1. (This is the 64 bit extension of the ARM architecture).

Run mysql docker container

$ docker run -d -p 3306:3306 —name [container_name] -e MYSQL_ROOT_PASSWORD=[password] mysql/mysql-server:latest-aarch64

-d : runs the container in detached mode
-p : publishes the container’s ports to the host
-e : sets the environment variables
—name : assigns a custom name to the container (that’s 2 dashes)

Example: 

$ docker run -d -p 3306:3306 —name mysql-db -e MYSQL_ROOT_PASSWORD=P@ssword mysql/mysql-server:latest-aarch64

To check it’s running, you can run:

docker ps -a

ps : list containers
-a : all containers
