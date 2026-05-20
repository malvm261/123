# Проверь DNS
nslookup ghcr.io
cat /etc/resolv.conf

# Перезапусти resolved
sudo systemctl restart systemd-resolved

# Или пропиши DNS напрямую
sudo nano /etc/resolv.conf

nameserver 8.8.8.8
nameserver 8.8.4.4


-----------------------------------------------------
elplatai) malvm@malvm-Atlas-H256:~/Документы/projects/ElplatAI$ docker compose build --no-cache app 
[+] Building 2.8s (9/15)                                                                                                                                               
 => [internal] load local bake definitions                                                                                                                        0.0s
 => => reading from stdin 587B                                                                                                                                    0.0s
 => [internal] load build definition from Dockerfile                                                                                                              0.0s
 => => transferring dockerfile: 464B                                                                                                                              0.0s
 => [internal] load metadata for docker.io/library/python:3.13-alpine                                                                                             0.6s
 => [internal] load metadata for ghcr.io/astral-sh/uv:0.5.31                                                                                                      0.4s
 => [internal] load .dockerignore                                                                                                                                 0.0s
 => => transferring context: 2B                                                                                                                                   0.0s
 => CACHED [stage-0 1/8] FROM docker.io/library/python:3.13-alpine@sha256:420cd0bf0f3998275875e02ecd5808168cf0843cbb4d3c536432f729247b2acc                        0.0s
 => => resolve docker.io/library/python:3.13-alpine@sha256:420cd0bf0f3998275875e02ecd5808168cf0843cbb4d3c536432f729247b2acc                                       0.0s
 => [internal] load build context                                                                                                                                 0.0s
 => => transferring context: 6.68kB                                                                                                                               0.0s
 => CACHED FROM ghcr.io/astral-sh/uv:0.5.31@sha256:7bff3c3776ec467fc1437960f2c469d8beb30f536a6465a3350c647ccd260ec2                                               0.0s
 => => resolve ghcr.io/astral-sh/uv:0.5.31@sha256:7bff3c3776ec467fc1437960f2c469d8beb30f536a6465a3350c647ccd260ec2                                                0.0s
 => ERROR [stage-0 2/8] RUN apk add --no-cache     gcc g++ musl-dev     libgl     glib     libgomp                                                                2.0s
------
 > [stage-0 2/8] RUN apk add --no-cache     gcc g++ musl-dev     libgl     glib     libgomp:
1.888 ERROR: unable to select packages:
1.888   libgl (no such package):
1.888     required by: world[libgl]
------
[+] build 0/1
 ⠙ Image elplatai-app Building                                                                                                                                     2.9s
Dockerfile:3

--------------------

   2 |     

   3 | >>> RUN apk add --no-cache \

   4 | >>>     gcc g++ musl-dev \

   5 | >>>     libgl \

   6 | >>>     glib \

   7 | >>>     libgomp

   8 |     

--------------------

failed to solve: process "/bin/sh -c apk add --no-cache     gcc g++ musl-dev     libgl     glib     libgomp" did not complete successfully: exit code: 1

(elplatai) malvm@malvm-Atlas-H256:~/Документы/projects/ElplatAI$ 
