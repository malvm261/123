i-server /mnt/raid/projects/ElplatAI # docker compose up --build -d app
[+] Building 62.5s (9/15)
 => [internal] load local bake definitions                                                                                                                                                                  0.0s
 => => reading from stdin 522B                                                                                                                                                                              0.0s
 => [internal] load build definition from Dockerfile                                                                                                                                                        0.2s
 => => transferring dockerfile: 665B                                                                                                                                                                        0.0s
 => [internal] load metadata for ghcr.io/astral-sh/uv:0.5.31                                                                                                                                                1.2s
 => [internal] load metadata for docker.io/library/python:3.13.12-slim-bookworm@sha256:a58daefb915e1e03ad48f3ca4df8832065412c5c35cacb9d39f4229184de12b6                                                     9.5s
 => [internal] load .dockerignore                                                                                                                                                                           0.1s
 => => transferring context: 2B                                                                                                                                                                             0.0s
 => [stage-0 1/8] FROM docker.io/library/python:3.13.12-slim-bookworm@sha256:a58daefb915e1e03ad48f3ca4df8832065412c5c35cacb9d39f4229184de12b6                                                              12.4s
 => => resolve docker.io/library/python:3.13.12-slim-bookworm@sha256:a58daefb915e1e03ad48f3ca4df8832065412c5c35cacb9d39f4229184de12b6                                                                       0.5s
 => => sha256:251fa4afca5fc2d7040789882e09a87df8ee39142886da6be499f5c047824efa 248B / 248B                                                                                                                  1.5s
 => => sha256:af650bea6b21577b4b85c68a0d827914840295c2b3fce5a7f4c2c8223a6f3425 12.48MB / 12.48MB                                                                                                            2.4s
 => => sha256:da539b6761059a0a114c6671f1267b57445e3a54da023db5c28be019e40f0284 28.24MB / 28.24MB                                                                                                            5.9s
 => => sha256:35ade6973e87c7a996978364cbfbae6f92581167bdf6a3bf54b4dc4549f40afa 3.52MB / 3.52MB                                                                                                              2.1s
 => => extracting sha256:da539b6761059a0a114c6671f1267b57445e3a54da023db5c28be019e40f0284                                                                                                                   0.8s
 => => extracting sha256:35ade6973e87c7a996978364cbfbae6f92581167bdf6a3bf54b4dc4549f40afa                                                                                                                   0.4s
 => => extracting sha256:af650bea6b21577b4b85c68a0d827914840295c2b3fce5a7f4c2c8223a6f3425                                                                                                                   0.5s
 => => extracting sha256:251fa4afca5fc2d7040789882e09a87df8ee39142886da6be499f5c047824efa                                                                                                                   1.2s
 => [internal] load build context                                                                                                                                                                           1.1s
 => => transferring context: 6.55kB                                                                                                                                                                         0.0s
 => CACHED FROM ghcr.io/astral-sh/uv:0.5.31@sha256:7bff3c3776ec467fc1437960f2c469d8beb30f536a6465a3350c647ccd260ec2                                                                                         0.8s
 => => resolve ghcr.io/astral-sh/uv:0.5.31@sha256:7bff3c3776ec467fc1437960f2c469d8beb30f536a6465a3350c647ccd260ec2                                                                                          0.5s
 => ERROR [stage-0 2/8] RUN apt-get update && apt-get install -y --no-install-recommends     build-essential gcc g++     ca-certificates     libgl1     libglib2.0-0     libgomp1     && rm -rf /var/lib/  38.8s
------
 > [stage-0 2/8] RUN apt-get update && apt-get install -y --no-install-recommends     build-essential gcc g++     ca-certificates     libgl1     libglib2.0-0     libgomp1     && rm -rf /var/lib/apt/lists/*:
31.12 Ign:1 http://deb.debian.org/debian bookworm InRelease
31.12 Ign:2 http://deb.debian.org/debian bookworm-updates InRelease
31.12 Ign:3 http://deb.debian.org/debian-security bookworm-security InRelease
32.12 Ign:1 http://deb.debian.org/debian bookworm InRelease
32.12 Ign:2 http://deb.debian.org/debian bookworm-updates InRelease
32.12 Ign:3 http://deb.debian.org/debian-security bookworm-security InRelease
34.12 Ign:1 http://deb.debian.org/debian bookworm InRelease
34.12 Ign:2 http://deb.debian.org/debian bookworm-updates InRelease
34.12 Ign:3 http://deb.debian.org/debian-security bookworm-security InRelease
38.12 Err:1 http://deb.debian.org/debian bookworm InRelease
38.12   Cannot initiate the connection to debian.map.fastlydns.net:80 (2a04:4e42:6b::644). - connect (101: Network is unreachable) Could not connect to debian.map.fastlydns.net:80 (199.232.174.132), connection timed out Cannot initiate the connection to deb.debian.org:80 (2a04:4e42:6b::644). - connect (101: Network is unreachable)
38.12 Err:2 http://deb.debian.org/debian bookworm-updates InRelease
38.12   Cannot initiate the connection to deb.debian.org:80 (2a04:4e42:6b::644). - connect (101: Network is unreachable)
38.12 Err:3 http://deb.debian.org/debian-security bookworm-security InRelease
38.12   Cannot initiate the connection to deb.debian.org:80 (2a04:4e42:6b::644). - connect (101: Network is unreachable)
38.12 Reading package lists...
38.13 W: Failed to fetch http://deb.debian.org/debian/dists/bookworm/InRelease  Cannot initiate the connection to debian.map.fastlydns.net:80 (2a04:4e42:6b::644). - connect (101: Network is unreachable) Could not connect to debian.map.fastlydns.net:80 (199.232.174.132), connection timed out Cannot initiate the connection to deb.debian.org:80 (2a04:4e42:6b::644). - connect (101: Network is unreachable)
38.13 W: Failed to fetch http://deb.debian.org/debian/dists/bookworm-updates/InRelease  Cannot initiate the connection to deb.debian.org:80 (2a04:4e42:6b::644). - connect (101: Network is unreachable)
38.13 W: Failed to fetch http://deb.debian.org/debian-security/dists/bookworm-security/InRelease  Cannot initiate the connection to deb.debian.org:80 (2a04:4e42:6b::644). - connect (101: Network is unreachable)
38.13 W: Some index files failed to download. They have been ignored, or old ones used instead.
38.32 Reading package lists...
38.32 Building dependency tree...
38.32 Reading state information...
38.32 E: Unable to locate package build-essential
38.32 E: Unable to locate package gcc
38.32 E: Unable to locate package libgl1
38.32 E: Unable to locate package libglib2.0-0
38.32 E: Couldn't find any package by glob 'libglib2.0-0'
38.32 E: Couldn't find any package by regex 'libglib2.0-0'
38.32 E: Unable to locate package libgomp1
------
Dockerfile:3

--------------------

   2 |

   3 | >>> RUN apt-get update && apt-get install -y --no-install-recommends \

   4 | >>>     build-essential gcc g++ \

   5 | >>>     ca-certificates \

   6 | >>>     libgl1 \

   7 | >>>     libglib2.0-0 \

   8 | >>>     libgomp1 \

   9 | >>>     && rm -rf /var/lib/apt/lists/*

  10 |

--------------------

failed to solve: process "/bin/sh -c apt-get update && apt-get install -y --no-install-recommends     build-essential gcc g++     ca-certificates     libgl1     libglib2.0-0     libgomp1     && rm -rf /var/lib/apt/lists/*" did not complete successfully: exit code: 100
