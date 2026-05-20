malvm@ai-server /mnt/raid/projects/ElplatAI $ docker run --rm python:3.13-slim-bookworm curl -v http://deb.debian.org
Unable to find image 'python:3.13-slim-bookworm' locally
3.13-slim-bookworm: Pulling from library/python
Digest: sha256:e4fa1f978c539608a10cdf74700ac32a3f719dfc6e8b6b6001da82deb36302a2
Status: Downloaded newer image for python:3.13-slim-bookworm
docker: Error response from daemon: failed to create task for container: failed to create shim task: OCI runtime create failed: runc create failed: unable to start container process: error during container init: exec: "curl": executable file not found in $PATH

Run 'docker run --help' for more information
