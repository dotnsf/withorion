# with Orion

## Overview

**Docker Compose** enablement for any nodejs app with **Eclipse Orion** editor to make them editable.


### How to run app in current directory with Eclipse Orion editor

- Install Node.js

  - https://nodejs.org/

- Install docker & docker-compose:

  - `$ curl -sSL https://get.docker.com | sh`

  - `$ sudo usermod -a -G docker pi`

- Pull Eclipse Orion image

  - `$ docker pull cloudeity/orion`

- Copy Dockerfile and docker-compose.yml to this directory

  - `$ cp Dockerfile APP_DIRECTORY`

  - `$ cp docker-compose.yml APP_DIRECTORY`

- Change directory to app, which supposed to be run on port 8080

  - `$ cd APP_DIRECTORY

  - If this app would need extra configuration in Dockerfile, edit it in this timing.

  - If this app would run on not port 8080, change docker-compose.yml port number.

- Install dependencies

  - `$ npm install`

- Build image

  - `$ docker-compose build`
  
- Run images

  - `docker-compose up -d`

- Access to app

  - `http://localhost:8080/`

- Access to orion

  - `http://localhost:8081/`


## Copyright

2021 [K.Kimura @ Juge.Me](https://github.com/dotnsf) all rights reserved.
