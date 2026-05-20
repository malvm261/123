malvm@ai-server /mnt/raid/projects/ElplatAI $ docker run --rm python:3.13-slim-bookworm apt-get update
Ign:1 http://deb.debian.org/debian bookworm InRelease
Ign:2 http://deb.debian.org/debian bookworm-updates InRelease
Ign:3 http://deb.debian.org/debian-security bookworm-security InRelease
Ign:1 http://deb.debian.org/debian bookworm InRelease
Ign:2 http://deb.debian.org/debian bookworm-updates InRelease
Ign:3 http://deb.debian.org/debian-security bookworm-security InRelease
Ign:1 http://deb.debian.org/debian bookworm InRelease
Ign:2 http://deb.debian.org/debian bookworm-updates InRelease
Ign:3 http://deb.debian.org/debian-security bookworm-security InRelease
Err:1 http://deb.debian.org/debian bookworm InRelease
  Could not connect to debian.map.fastlydns.net:80 (199.232.174.132), connection timed out Unable to connect to deb.debian.org:http:
Err:2 http://deb.debian.org/debian bookworm-updates InRelease
  Unable to connect to deb.debian.org:http:
Err:3 http://deb.debian.org/debian-security bookworm-security InRelease
  Unable to connect to deb.debian.org:http:
Reading package lists...
W: Failed to fetch http://deb.debian.org/debian/dists/bookworm/InRelease  Could not connect to debian.map.fastlydns.net:80 (199.232.174.132), connection timed out Unable to connect to deb.debian.org:http:
W: Failed to fetch http://deb.debian.org/debian/dists/bookworm-updates/InRelease  Unable to connect to deb.debian.org:http:
W: Failed to fetch http://deb.debian.org/debian-security/dists/bookworm-security/InRelease  Unable to connect to deb.debian.org:http:
W: Some index files failed to download. They have been ignored, or old ones used instead.
malvm@ai-server /mnt/raid/projects/ElplatAI $
