# dockerfiles-centos-nginx

CentOS Dockerfile for nginx


## Build

Copy the sources down and do the build

```
# docker build --rm -t <username>/nginx .
```

## Usage

To run (if port 8080 is available and open on your host):

```
# docker run -d -p 8080:80 <username>/nginx
```

or to assign a random port that maps to port 80 on the container:

```
# docker run -d -p 80 <username>/nginx
```

To the port that the container is listening on:

```
# docker ps
```

## Test

```
# curl http://localhost:8080
```
