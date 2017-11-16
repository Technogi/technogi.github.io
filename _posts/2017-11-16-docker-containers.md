---
layout: post
title:  "Docker Containers"
date:   2017-11-16 03:01:27
description: Docker Containers.
categories:
- micro trainning
- docker
- containers
permalink: docker-containers
author: Juan Francisco
---
## Contenedores
- Un contenedor consta de un entorno de ejecución completo: una aplicación, más todas sus dependencias, bibliotecas y otros archivos binarios y de configuración necesarios para ejecutarlo, agrupados en un solo paquete.

  ![Containers vs VMs](../images/docker-virtual-machines-container.png?raw=true "Containers vs Vitual Machines")

## Ventajas
- Hardware-agnostic
- Content-Agnostic
- Content Isolation
- Automation
- Highly Efficient

## Docker
- Docker es una plataforma abierta para que los desarrolladores y administradores de sistemas construyan, envíen y ejecuten aplicaciones distribuidas, ya sea en computadoras portátiles, máquinas virtuales en centros de datos o en la nube.

  ![Docker Execution](../images/docker-from-dev-to-ops.png?raw=true "Docker Execution")

  ![Docker Lifecycle](../images/docker-stages.png?raw=true "Docker Lifecycle")

  ![Docker Lifecycle-Cont](../images/docker-pull-deploy.png?raw=true "Docker Lifecycle Cont")

## Ejemplo
package.json
````
{
  "name": "hello-docker",
  "version": "1.0.0",
  "description": "Hello Docker",
  "main": "server.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node server.js"
  },
  "keywords": [
    "docker"
  ],
  "author": "Juan Francisco Alvarez Urquijo <paco@technogi.com.mx>",
  "license": "MIT",
  "dependencies": {
    "express": "^4.13.3"
  }
}  
````

Dockerfile
````
FROM node:boron
MAINTAINER Juan Francisco Alvarez Urquijo <paco@technogi.com.mx>

# Create app directory
WORKDIR /usr/src/app

# Install app dependencies
COPY package.json .
# For npm@5 or later, copy package-lock.json as well
# COPY package.json package-lock.json ./

RUN npm install
# If you are building your code for production
# RUN npm install --only=production

# Bundle app source
COPY . .

EXPOSE 8080
CMD [ "npm", "start" ]
````

- Construcción de imagen y ejecución de contenedor
````
docker build -t fkone/node-web-app .

docker run -p 49160:8080 --name node-web-app -it -d fkone/node-web-app

curl -i localhost:49160
````

Envío de Imagen a Repositorio de Imágenes
````
docker login

docker push fkone/node-web-app
````

## Enlaces recomendados
- [Docker](https://www.docker.com/)
- [Dockerizing a Node.js web app](https://nodejs.org/en/docs/guides/nodejs-docker-webapp/)
