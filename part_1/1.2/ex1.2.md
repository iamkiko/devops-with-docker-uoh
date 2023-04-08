## 1.2
```
$ docker rm boring_payne                                                                                                                                                 ✔  system 
boring_payne

$ docker rm quirky_ptolemy                                                                                                                                               ✔  system 
quirky_ptolemy

$ docker rm hardcore_sanderson                                                                                                                                           ✔  system 
Error response from daemon: You cannot remove a running container 8c9dce3d219b4d9e9d957221786488825b469eb634cd971764e7fbb0eeadb51e. Stop the container before attempting removal or force remove

$ docker stop hardcore_sanderson                                                                                                                                       1 ✘  system 
hardcore_sanderson

$ docker rm hardcore_sanderson                                                                                                                                           ✔  system 
hardcore_sanderson
```
