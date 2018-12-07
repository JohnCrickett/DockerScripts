To build an image:
```
docker build -t <image name> -f <path>/Dockerfile <path>/
```
or:
```
docker-compose build
```

To list images:
```
docker images
```

To remove an image:
```
docker image rm <image name>
```

To run the image (detached) if it doesn't have a service already running (i.e. no ENTRYPOINT)

```
docker run -it -d --name <container name> <image name> /bin/bash
```

To run an executable / command on the container
```
docker exec -it <container name> <executable>
```
or:
```
docker compose up
```

You can set environment variables in a service’s containers with the -e option, i.e.:

```
docker run -e VARIABLE=VALUE ...
```

i.e. to get a bash shell:
```
docker exec -it <container name> /bin/bash
```

to stop the container
```
docker stop <container name>
```
or if run with -d:
```
docker-compose stop
```
otherwise:
```
docker-compose down
```

to remove the container
```
docker rm <container name>
```

To run the container mounting a local folder with no service (drop bash if there's a running service).

```
docker run -it -d -v <full local path>:/<host path> --name <cointainer name> <image name> /bin/bash
```

To list containers:
```
docker container ls --all
```

Tidying up if you run out of space:
```
docker rm $(docker ps -q -f 'status=exited')
docker rmi $(docker images -q -f "dangling=true")
docker volume rm $(docker volume ls -qf dangling=true)
```
