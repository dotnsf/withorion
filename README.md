# with Orion

## Overview

**Docker Compose** enablement for any nodejs app with **Eclipse Orion** editor to make them editable.


## How to run app in current directory with Eclipse Orion editor

### Method 1 : Use Eclipse Orion as docker container. 

- Install Node.js

  - https://nodejs.org/

- Install docker & docker-compose:

  - `$ curl -sSL https://get.docker.com | sh`

  - `$ sudo usermod -a -G docker pi`

- Pull Eclipse Orion image

  - `$ docker pull cloudeity/orion`

- Change directory to app, which supposed to be run on port 8080

  - `$ cd APP_DIRECTORY`

- If needed, install dependent libraries

  - `$ npm install`

- Run application

  - `$ npm start`

- Open anohter terminal, and run Eclipse Orion on docker in port 8081 with current directory mounted as workspace.

  - `$ docker run -d --name orion -v ``pwd``:/opt/orion.client/modules/orionode/.workspace -p 8081:8081 cloudeity/orion`

- Access to app

  - `http://localhost:8080/`

- Access to orion

  - `http://localhost:8081/`


### Method 2 : Use docker-compose.yml and Dockerfile in this project. 

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

  - `$ cd APP_DIRECTORY`

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
