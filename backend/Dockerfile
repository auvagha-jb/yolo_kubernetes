# Get the base node image
FROM node:16-alpine 

LABEL maintainer="Jerry Auvagha <jerry.auvagha@student.moringaschool.com>"

# Set the working directory to /client
WORKDIR /backend

# Copy all files to the working directory
COPY ./ /backend

# Install dependencies
RUN npm install