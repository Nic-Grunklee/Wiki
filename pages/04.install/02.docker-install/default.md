---
title: 'Docker Install'
---

### Introduction

The Kavita team does offer an official Docker image which is automatically updated based on changes to [GitHub](https://github.com/Kareadita/Kavita).

#### 1. Kavita on Docker Hub

[Kizaing/KavitaDocker](https://hub.docker.com/r/kizaing/kavita)

#### 2. Docker Install


Running your Kavita server in docker is super easy! Barely an inconvenience. You can run the `:latest` stable version with this command:
```
docker run --name kavita -p 5000:5000 \
-v /your/manga/directory:/manga \
-v /kavita/data/directory:/kavita/data \
--restart unless-stopped \
-d kizaing/kavita:latest
```
You can also run it via the docker-compose file:
```
version: '3.9'
services:
    kavita:
        image: kizaing/kavita:latest
        volumes:
            - ./manga:/manga
            - ./data:/kavita/data
        ports:
            - "5000:5000"
        restart: unless-stopped
```
!  **Note**: Kavita is under heavy development and is being updated all the time, so the tag for current builds is `:nightly`. The :latest tag will be the latest stable release. There is also the `:alpine` tag if you want a smaller image, but it is only available for x64 systems.