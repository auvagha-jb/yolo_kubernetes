# Get the base node image
FROM node:16-alpine 

LABEL maintainer="Jerry Auvagha <jerry.auvagha@student.moringaschool.com>"

# Set the working directory to /client
WORKDIR /client

# Copy all files to the working directory
COPY ./ /client

# Install dependencies
RUN npm install
