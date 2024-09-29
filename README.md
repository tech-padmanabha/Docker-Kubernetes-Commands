# Docker & Kubernates

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

