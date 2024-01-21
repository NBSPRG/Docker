# It's an configuration file.
# We are going to form an image of it to run it on a container

FROM ubuntu

# This will install node js in our base image ubuntu
RUN apt-get update
RUN apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash -
RUN apt-get upgrade -y
RUN apt-get install -y nodejs

WORKDIR /app
# COPY source, destination
COPY package.json package.json 
COPY package-lock.json package-lock.json


RUN cd app && npm install

COPY main.js main.js

ENTRYPOINT ["node", "main.js"]

# FROM node as build

# WORKDIR app/

# RUN npm install

# COPY . .


# ENTRYPOINT ["node", "main.js"]

# Try multi stage build 
# write the own pipeline to have a grip on it
