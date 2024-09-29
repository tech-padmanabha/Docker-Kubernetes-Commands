# Docker & Kubernates


### Basic Commands
> docker run busybox echo hello bhai (it will find from local local if not available then download from docker hub and run)
> docker ps --all (get the history details of all)
|CONTAINER ID|   IMAGE     |COMMAND              |   CREATED     |STATUS                      |PORTS     |NAMES			|
|3c2ed4ae7638   |busybox   |"ping www.google.com" |  6 minutes ago    |Exited (0) 5 minutes ago|              |friendly_khayyam|
|157be6287bdd   |busybox   |"echo hello bhai"|       11 minutes ago   |Exited (0) |11 minutes ago|             |nervous_ride|

> docker create busybox
> docker start 157be6287bdd
`157be6287bdd`

> docker start -a 157be6287bdd (it starts and provides the abrivation of image)
`hello bhai`
> docker logs 157be6287bdd (for getting the logs)

> docker stop 1ade4e344b34 (It will noramly stop the container by shutdown/close all the dependencies)

> docker kill 1ade4e344b34 (It will kill the container quickly with out worring about dependencies closed or not)

> docker system prune 
```command
WARNING! This will remove:
  - all stopped containers
  - all networks not used by at least one container
  - all dangling images
  - unused build cache

Are you sure you want to continue? [y/N] y
Deleted Containers:
3c2ed4ae7638aacbbfec35c36527faa108a687ac7db1da2f259e82ca8cff325f
157be6287bdd5c530e20e792b808cd0d4b366338f6040846ce871363e4dc0867
```
### mysql database in docker 

> docker pull mysql:8.4 ( Pull from docker hub)
> docker run mysql:8.4  (Here we'll get some information what are required things, we need to provide)
You need to specify one of the following as an environment variable:
    - MYSQL_ROOT_PASSWORD
    - MYSQL_ALLOW_EMPTY_PASSWORD
    - MYSQL_RANDOM_ROOT_PASSWORD
> docker run --name test-sql -e MYSQL_ROOT_PASSWORD=password -d mysql:8.4
+ -e ENV_VARIABLE=value: the `-e` tag creates an environment variable that will be accessible within the container
+ -d: short for detached, the `-d` tag makes the container run in the background. If you remove this tag, the command will keep printing logs until the container stops.
+ --name CONTAINER_NAME: gives the container a name. The name should be readable and short. In our case, the name is test-sql.
+ run: creates a new container or starts an existing one

> [!NOTE]
> To access the terminal inside your container, you can use the following command:
> `$ docker exec -it container_name bash`
> `$ docker exec -it container_name sh` to enter inside the container command prompt( to exit type `exit` or press ctrl+d)

or
> docker run -it container_name sh/base/powershell/zsh(one of them) (After running the container directly enter inside the terminal)

folow the bellow steps :
Inside the base we need to provide `mysql -u root -p` and the password we need to provide
Then we can check the mysql data base information like 
```sql
SHOW SCHEMAS: Lists all schemas in the MySQL instance
USE SCHEMAS_NAME;
SHOW TABLES;  Lists all tables in the schema;
```
> [!WARNING]
> Just fallow the mysql version properly before going to work with mysql

## Docker Commands 

```
Docker container ls (it’ll show the list of container)
Docker logs -f 394920f( profide the container id)
Docker images (it’ll show how many images are there)
Docker container ls -a (it’ll show all the container)
Docker container stop id_of_container (It ll stop the container normally)
Docker container kill id_of_container (It ll stop without worring about system setup)
```
> Some traking commands 

```
#docker run -p5000:5000 in28min/todo-rest-api-h2:1.0.0.RELEASE
#docker tag in28min/todo-rest-api-h2:1.0.0.RELEASE in28min/todo-rest-api-h2:latest (change tag)
#docker pull mysql (Here pull command use for download from global to local repository)
#docker search mysql(for searching for official release sing(OK))
#docker image histry image_id/repository-name:tag (for getting the histry of image)
#docker image inspect image_id/repository-name:tag(for getting the configuration info)
# docker image remove id/repository-name:tag (for delete image)
Container commands
# docker container run -p5000:5000 -d in28min/todo-rest-api-h2:1.0.0.RELEASE (-p(port)
or -d(detached mode) repo: tag docker container kill 440b)
# docker container pause b0f28 (for pause the application)
# docker container unpause b0f28 (for resume the application)
# docker container ls (for running container list here we get the container id)
# docker container ls -a (for there are any stopped container)
# docker container logs b0f28 (for getting the container log statements)
# docker container inspect b0f2817e9cde (for getting the config info)
# docker container prune(it will remove all the stopped container)
# docker container stop b0f (it will stop normal mode with gracefully shutting down
everything related application)
# docker container kill 440b (it will immediately terminate the process doesn’t bother
about shutting down)
# docker container run -p5000:5000 -d --restart=always in28min/todo-rest-apih2:1.0.0.RELEASE( docker daemon start it will automatic started by default. We can
provide 0 also)
# docker container –help (here you will get more helpful commands for other works)
#docker events (It’ll provides information about docker, what’s are happing inside
docker)
# docker top 9c770 (what are the files for running information)
# docker container run -p5001:5000 -m 513m --cpu-quota 5000 -d in28min/todo-restapi-h2:1.0.0.RELEASE ( Just watch the limit or CPU in bellow diagram, here “-m” is
memory (512m=512MegaByte 1G=1024MegaByte) or “—cpu-quota” is the CPU(100000
= 100% or 5000=5%) use
#docker stats 9c770 (Provide stats about CPU, Memory it take in server)
#docker system df (What are in Docker Defend things are in Docker Daemon Manager)
```

> Explore

