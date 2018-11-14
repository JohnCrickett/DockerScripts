To build an image:
```
docker build -t <image name> -f <path>/Dockerfile <path>/
```

To run the image if it doesn't have a service already running

```
docker run -it -d --name <container name> <image name> /bin/bash
```

To run an executable / command on the container
```
docker exec -it <container name> <executable>
```

i.e. to get a bash shell:
```
docker exec -it pcbats /bin/bash
```

to stop the container
```
docker stop <container name>
```

to remove the container
```
docker rm <container name>
```

To run the container mounting a local folder with no service (drop bash if there's a running service).

```
docker run -it -d -v <full local path>:/<host path> --name <cointainer name> <image name> /bin/bash
```
