---
date: "2024-09-11T22:30:51+00:00"
title: "Mixxx with Icecast TLS Support Inside Docker"
---

Go to [https://github.com/mixxxdj/mixxx/actions/runs/9238476537?pr=13285](https://github.com/mixxxdj/mixxx/actions/runs/9238476537?pr=13285) and download _Ubuntu 22.04 Qt6 DEB.zip_ ( [https://github.com/mixxxdj/mixxx/actions/runs/9238476537/artifacts/1537877751](https://github.com/mixxxdj/mixxx/actions/runs/9238476537/artifacts/1537877751)). Extract the ZIP file to get the _mixxx-2.5-alpha-397-g8c8c12eb20.deb_ file.

### Dockerfile

```dockerfile
# By Abdullah As-Sadeed

# Start from an Ubuntu 22.04 image
FROM ubuntu:22.04

# Update package list, upgrade installed packages, and install required packages
RUN apt update && apt dist-upgrade -y && apt install -y gdebi-core ca-certificates

# Copy the .deb package into the container
COPY mixxx-2.5-alpha-397-g8c8c12eb20.deb /tmp

# Install the .deb package
RUN gdebi -n /tmp/mixxx-2.5-alpha-397-g8c8c12eb20.deb

# Clean up
RUN apt clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

# Set the DISPLAY environment variable
ENV DISPLAY=unix$DISPLAY

# Run Mixxx
CMD ["mixxx"]
```

## Start.sh

```sh
#!/bin/bash

# By Abdullah As-Sadeed

# Build container image
docker build -t mixxx .

# Allow docker to connect to X server
xhost +local:docker

# Run container
docker run -it --rm -e DISPLAY=$DISPLAY \
    -e XDG_RUNTIME_DIR=/tmp/runtime-root \
    -v /tmp/.X11-unix:/tmp/.X11-unix \
    -v /dev/snd:/dev/snd --privileged \
    -v ~/Music:/root/Music \
    -v /tmp/.mixxx:/root/.mixxx \
    mixxx
```
