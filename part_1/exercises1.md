## Exercises for Part 1

Source material: [Part 1](https://devopswithdocker.com/part-1)
### 1.1

```
$ docker ps -a                                                                                                                                                           ✔  system 
CONTAINER ID
IMAGE     COMMAND                  CREATED              STATUS                      PORTS     NAMES
32363cc9d6e4   nginx     "/docker-entrypoint.…"   About a minute ago   Exited (0) 19 seconds ago             boring_payne
1a4315e6bf9c   nginx     "/docker-entrypoint.…"   About a minute ago   Exited (0) 6 seconds ago              quirky_ptolemy
```
### 1.2
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

### 1.3

Secret message:
```Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-12-16 14:44:00 +0000 UTC
2022-12-16 14:44:02 +0000 UTC
2022-12-16 14:44:04 +0000 UTC
2022-12-16 14:44:06 +0000 UTC
2022-12-16 14:44:08 +0000 UTC
```
Commands:
```
 $ docker run devopsdockeruh/simple-web-service:ubuntu
 $ docker ps -a
 $ docker attach --no-stdin beautiful_cerf

 $ docker exec -it beautiful_cerf bash
```

### 1.4
```
$ docker run -d -it --name dme1 ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website\;'
3f7ebd68c76fe447620fee12d0c2a6087476946617057292d22b001bcc87c71c
$ docker exec -it dme1 bash                                     ✔  system 
root@3f7ebd68c76f:/# apt-get update
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy InRelease [270 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy-updates InRelease [114 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy-backports InRelease [99.8 kB]
Get:4 http://ports.ubuntu.com/ubuntu-ports jammy-security InRelease [110 kB]
Get:5 http://ports.ubuntu.com/ubuntu-ports jammy/multiverse arm64 Packages [224 kB]
Get:6 http://ports.ubuntu.com/ubuntu-ports jammy/restricted arm64 Packages [24.2 kB]
Get:7 http://ports.ubuntu.com/ubuntu-ports jammy/universe arm64 Packages [17.2 MB]
Get:8 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 Packages [1758 kB]
Get:9 http://ports.ubuntu.com/ubuntu-ports jammy-updates/restricted arm64 Packages [256 kB]
Get:10 http://ports.ubuntu.com/ubuntu-ports jammy-updates/universe arm64 Packages [837 kB]
Get:11 http://ports.ubuntu.com/ubuntu-ports jammy-updates/multiverse arm64 Packages [2315 B]
Get:12 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 Packages [889 kB]
Get:13 http://ports.ubuntu.com/ubuntu-ports jammy-backports/main arm64 Packages [3511 B]
Get:14 http://ports.ubuntu.com/ubuntu-ports jammy-backports/universe arm64 Packages [7269 B]
Get:15 http://ports.ubuntu.com/ubuntu-ports jammy-security/restricted arm64 Packages [243 kB]
Get:16 http://ports.ubuntu.com/ubuntu-ports jammy-security/universe arm64 Packages [646 kB]
Get:17 http://ports.ubuntu.com/ubuntu-ports jammy-security/main arm64 Packages [592 kB]
Fetched 23.3 MB in 6s (3847 kB/s)
Reading package lists... Done
root@3f7ebd68c76f:/# apt install curl
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  ca-certificates libbrotli1 libcurl4 libldap-2.5-0 libldap-common libnghttp2-14
  libpsl5 librtmp1 libsasl2-2 libsasl2-modules libsasl2-modules-db libssh-4
  openssl publicsuffix
Suggested packages:
  libsasl2-modules-gssapi-mit | libsasl2-modules-gssapi-heimdal
  libsasl2-modules-ldap libsasl2-modules-otp libsasl2-modules-sql
The following NEW packages will be installed:
  ca-certificates curl libbrotli1 libcurl4 libldap-2.5-0 libldap-common
  libnghttp2-14 libpsl5 librtmp1 libsasl2-2 libsasl2-modules libsasl2-modules-db
  libssh-4 openssl publicsuffix
0 upgraded, 15 newly installed, 0 to remove and 0 not upgraded.
Need to get 2928 kB of archives.
After this operation, 6762 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 openssl arm64 3.0.2-0ubuntu1.7 [1160 kB]
Get:2 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 ca-certificates all 20211016ubuntu0.22.04.1 [144 kB]
Get:3 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libnghttp2-14 arm64 1.43.0-1build3 [75.4 kB]
Get:4 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libpsl5 arm64 0.21.0-1.2build2 [58.3 kB]
Get:5 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 publicsuffix all 20211207.1025-1 [129 kB]
Get:6 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libbrotli1 arm64 1.0.9-2build6 [314 kB]
Get:7 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libsasl2-modules-db arm64 2.1.27+dfsg2-3ubuntu1 [21.3 kB]
Get:8 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libsasl2-2 arm64 2.1.27+dfsg2-3ubuntu1 [55.6 kB]
Get:9 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libldap-2.5-0 arm64 2.5.13+dfsg-0ubuntu0.22.04.1 [181 kB]
Get:10 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 librtmp1 arm64 2.4+20151223.gitfa8646d.1-2build4 [59.2 kB]
Get:11 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libssh-4 arm64 0.9.6-2build1 [184 kB]
Get:12 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libcurl4 arm64 7.81.0-1ubuntu1.6 [284 kB]
Get:13 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 curl arm64 7.81.0-1ubuntu1.6 [190 kB]
Get:14 http://ports.ubuntu.com/ubuntu-ports jammy-updates/main arm64 libldap-common all 2.5.13+dfsg-0ubuntu0.22.04.1 [15.9 kB]
Get:15 http://ports.ubuntu.com/ubuntu-ports jammy/main arm64 libsasl2-modules arm64 2.1.27+dfsg2-3ubuntu1 [57.3 kB]
Fetched 2928 kB in 2s (1604 kB/s)
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package openssl.
(Reading database ... 4389 files and directories currently installed.)
Preparing to unpack .../00-openssl_3.0.2-0ubuntu1.7_arm64.deb ...
Unpacking openssl (3.0.2-0ubuntu1.7) ...
Selecting previously unselected package ca-certificates.
Preparing to unpack .../01-ca-certificates_20211016ubuntu0.22.04.1_all.deb ...
Unpacking ca-certificates (20211016ubuntu0.22.04.1) ...
Selecting previously unselected package libnghttp2-14:arm64.
Preparing to unpack .../02-libnghttp2-14_1.43.0-1build3_arm64.deb ...
Unpacking libnghttp2-14:arm64 (1.43.0-1build3) ...
Selecting previously unselected package libpsl5:arm64.
Preparing to unpack .../03-libpsl5_0.21.0-1.2build2_arm64.deb ...
Unpacking libpsl5:arm64 (0.21.0-1.2build2) ...
Selecting previously unselected package publicsuffix.
Preparing to unpack .../04-publicsuffix_20211207.1025-1_all.deb ...
Unpacking publicsuffix (20211207.1025-1) ...
Selecting previously unselected package libbrotli1:arm64.
Preparing to unpack .../05-libbrotli1_1.0.9-2build6_arm64.deb ...
Unpacking libbrotli1:arm64 (1.0.9-2build6) ...
Selecting previously unselected package libsasl2-modules-db:arm64.
Preparing to unpack .../06-libsasl2-modules-db_2.1.27+dfsg2-3ubuntu1_arm64.deb ...
Unpacking libsasl2-modules-db:arm64 (2.1.27+dfsg2-3ubuntu1) ...
Selecting previously unselected package libsasl2-2:arm64.
Preparing to unpack .../07-libsasl2-2_2.1.27+dfsg2-3ubuntu1_arm64.deb ...
Unpacking libsasl2-2:arm64 (2.1.27+dfsg2-3ubuntu1) ...
Selecting previously unselected package libldap-2.5-0:arm64.
Preparing to unpack .../08-libldap-2.5-0_2.5.13+dfsg-0ubuntu0.22.04.1_arm64.deb ...
Unpacking libldap-2.5-0:arm64 (2.5.13+dfsg-0ubuntu0.22.04.1) ...
Selecting previously unselected package librtmp1:arm64.
Preparing to unpack .../09-librtmp1_2.4+20151223.gitfa8646d.1-2build4_arm64.deb ...
Unpacking librtmp1:arm64 (2.4+20151223.gitfa8646d.1-2build4) ...
Selecting previously unselected package libssh-4:arm64.
Preparing to unpack .../10-libssh-4_0.9.6-2build1_arm64.deb ...
Unpacking libssh-4:arm64 (0.9.6-2build1) ...
Selecting previously unselected package libcurl4:arm64.
Preparing to unpack .../11-libcurl4_7.81.0-1ubuntu1.6_arm64.deb ...
Unpacking libcurl4:arm64 (7.81.0-1ubuntu1.6) ...
Selecting previously unselected package curl.
Preparing to unpack .../12-curl_7.81.0-1ubuntu1.6_arm64.deb ...
Unpacking curl (7.81.0-1ubuntu1.6) ...
Selecting previously unselected package libldap-common.
Preparing to unpack .../13-libldap-common_2.5.13+dfsg-0ubuntu0.22.04.1_all.deb ...
Unpacking libldap-common (2.5.13+dfsg-0ubuntu0.22.04.1) ...
Selecting previously unselected package libsasl2-modules:arm64.
Preparing to unpack .../14-libsasl2-modules_2.1.27+dfsg2-3ubuntu1_arm64.deb ...
Unpacking libsasl2-modules:arm64 (2.1.27+dfsg2-3ubuntu1) ...
Setting up libpsl5:arm64 (0.21.0-1.2build2) ...
Setting up libbrotli1:arm64 (1.0.9-2build6) ...
Setting up libsasl2-modules:arm64 (2.1.27+dfsg2-3ubuntu1) ...
Setting up libnghttp2-14:arm64 (1.43.0-1build3) ...
Setting up libldap-common (2.5.13+dfsg-0ubuntu0.22.04.1) ...
Setting up libsasl2-modules-db:arm64 (2.1.27+dfsg2-3ubuntu1) ...
Setting up librtmp1:arm64 (2.4+20151223.gitfa8646d.1-2build4) ...
Setting up libsasl2-2:arm64 (2.1.27+dfsg2-3ubuntu1) ...
Setting up libssh-4:arm64 (0.9.6-2build1) ...
Setting up openssl (3.0.2-0ubuntu1.7) ...
Setting up publicsuffix (20211207.1025-1) ...
Setting up libldap-2.5-0:arm64 (2.5.13+dfsg-0ubuntu0.22.04.1) ...
Setting up ca-certificates (20211016ubuntu0.22.04.1) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 78.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/aarch64-linux-gnu/perl/5.34.0 /usr/local/share/perl/5.34.0 /usr/lib/aarch64-linux-gnu/perl5/5.34 /usr/share/perl5 /usr/lib/aarch64-linux-gnu/perl-base /usr/lib/aarch64-linux-gnu/perl/5.34 /usr/share/perl/5.34 /usr/local/lib/site_perl) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Updating certificates in /etc/ssl/certs...
124 added, 0 removed; done.
Setting up libcurl4:arm64 (7.81.0-1ubuntu1.6) ...
Setting up curl (7.81.0-1ubuntu1.6) ...
Processing triggers for libc-bin (2.35-0ubuntu3.1) ...
Processing triggers for ca-certificates (20211016ubuntu0.22.04.1) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...
done.
root@3f7ebd68c76f:/# curl helsinki.fi
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="https://www.helsinki.fi/">here</a>.</p>
</body></html>
root@3f7ebd68c76f:/#
```
### 1.5/1.6

```
$  docker run -it devopsdockeruh/pull_exercise                                                    INT ✘  2m 13s  system 
Unable to find image 'devopsdockeruh/pull_exercise:latest' locally
latest: Pulling from devopsdockeruh/pull_exercise
8e402f1a9c57: Pull complete
5e2195587d10: Pull complete
6f595b2fc66d: Pull complete
165f32bf4e94: Pull complete
67c4f504c224: Pull complete
Digest: sha256:7c0635934049afb9ca0481fb6a58b16100f990a0d62c8665b9cfb5c9ada8a99f
Status: Downloaded newer image for devopsdockeruh/pull_exercise:latest
WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested
Give me the password: b_____
You found the correct password. Secret message is:
"This is the secret message"

```
