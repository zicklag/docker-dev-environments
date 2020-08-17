# Docker Dev Environments

This repo contains Docker images and helpers for running development environments using Docker. I'm currently messing around with using Docker for my [Tauri](https://tauri.studio) development environment. I'm not root on my machine so this works really well with [Rootless Docker](https://docs.docker.com/engine/security/rootless/).

## `docker-env` Script

The `docker-env` script runs a docker image that you specify in privileged mode with, all your environment variables set, your whole home dir mounted and your workdir set to your current \$PWD. This means you can essentially just start a container environment in your current directory where you have the same home dir and environment, but a different system environment. You will look like root in the container and you can rut apt install and stuff, but you won't actually be root and when you exit the container everything will be owned by your username again ( assuming you are running rootless Docker ).

```bash
# Run this and now you're root on ubuntu:18.04, but in your home directory and environment variables
docker-env ubuntu:18.04
```

## Proxy Cert

I'm also behind an HTTPS proxy with SSL Bump so I have my proxy cert in here. You won't want to use that.
