## 1.5
```
$ docker pull devopsdockeruh/simple-web-service:ubuntu                                                                                                             INT ✘  7m 34s  system   11:58:19
ubuntu: Pulling from devopsdockeruh/simple-web-service
Digest: sha256:d44e1dce398732e18c7c2bad9416a072f719af33498302b02929d4c112e88d2a
Status: Image is up to date for devopsdockeruh/simple-web-service:ubuntu
docker.io/devopsdockeruh/simple-web-service:ubuntu

$ docker images                                                                                                                                                            ✔  3s  system   11:59:11
REPOSITORY                                  TAG            IMAGE ID       CREATED          SIZE
devopsdockeruh/simple-web-service           ubuntu         4e3362e907d5   2 years ago      83MB
devopsdockeruh/simple-web-service           alpine         fd312adc88e0   2 years ago      15.7MB

$ docker run -d --name alpine devopsdockeruh/simple-web-service:alpine                                                                                                          ✔  system   11:59:28
WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested
21631ac350865620c3634c7a6ec28311db964067f0e348d21713910c66d8dba9

$ docker exec -it alpine sh                                                                                                                                                     ✔  system   12:00:25

$ /usr/src/app # ls
server    text.log
/usr/src/app # tail -f ./text.log
2023-03-28 10:00:31 +0000 UTC
2023-03-28 10:00:33 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2023-03-28 10:00:35 +0000 UTC
2023-03-28 10:00:37 +0000 UTC
2023-03-28 10:00:39 +0000 UTC
2023-03-28 10:00:41 +0000 UTC
2023-03-28 10:00:43 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
```
