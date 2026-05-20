(elplatai) malvm@malvm-Atlas-H256:~/Документы/projects/ElplatAI$ docker compose build --no-cache app 
[+] Building 0.2s (4/4) FINISHED                                                                                                                                       
 => [internal] load local bake definitions                                                                                                                        0.0s
 => => reading from stdin 587B                                                                                                                                    0.0s
 => [internal] load build definition from Dockerfile                                                                                                              0.0s
 => => transferring dockerfile: 464B                                                                                                                              0.0s
 => CANCELED [internal] load metadata for docker.io/library/python:3.13-alpine                                                                                    0.0s
 => ERROR [internal] load metadata for ghcr.io/astral-sh/uv:0.5.31                                                                                                0.0s
------
 > [internal] load metadata for ghcr.io/astral-sh/uv:0.5.31:
------
[+] build 0/1
 ⠙ Image elplatai-app Building                                                                                                                                     0.2s
Dockerfile:9

--------------------

   7 |         libgomp

   8 |     

   9 | >>> COPY --from=ghcr.io/astral-sh/uv:0.5.31 /uv /usr/local/bin/

  10 |     

  11 |     WORKDIR /project

--------------------

failed to solve: failed to fetch anonymous token: Get "https://ghcr.io/token?scope=repository%3Aastral-sh%2Fuv%3Apull&service=ghcr.io": dial tcp: lookup ghcr.io on 127.0.0.53:53: no such host

(elplatai) malvm@malvm-Atlas-H256:~/Документы/projects/ElplatAI$ 
