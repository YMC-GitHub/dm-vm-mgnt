# quickly start docker

##### \#~~desc~~
start and active docker, then connect to docker-deamon quickly with docker-machine in shell.

##### \#~~conf~~
define your docker-machine name in `conf.sh`,here is the `default` machine:
```
my_vm_name=default
```

##### \#~~usage~~
you can run as below:
```
# way 1:
$ cd /to/your/start.sh/path
$ bash ./start.sh
```

##### \#~~note~~
my pc is win7-64bt, and i use docker 12.x .with some reasons i have to start  docker with tty step by step . so i write this shell script. now share with you!
my environment:
```
$ docker version
Client:
 Version:      1.12.6
 API version:  1.24
 Go version:   go1.6.4
 Git commit:   78d1802
 Built:        Wed Jan 11 00:23:16 2017
 OS/Arch:      windows/amd64

An error occurred trying to connect: Get http://%2F%2F.%2Fpipe%2Fdocker_engine/v1.24/version: open //./pipe/docker_engine: The system cannot find the file specified.


$ docker-machine version
docker-machine.exe version 0.8.2, build e18a919

$ docker-compose version
docker-compose version 1.22.0, build f46880f
docker-py version: 3.5.0
CPython version: 2.7.15
OpenSSL version: OpenSSL 1.0.2o  27 Mar 2018
```

if you are careful ,you would find that An error occurred when i run `docker version` in win7 ,not docker2box.// run as below to solve it:
```
$ docker-machine ssh default "docker version"

# or
$ docker-machine ssh default
$ docker version

# or (best)
docker-machine ssh default << eof
docker version
eof
```
if you are more careful , having do as above, you would also find a funny thing here!