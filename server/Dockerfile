# set up base image
FROM node:14.14.0-alpine

#set up work directory
WORKDIR '/app'

#install dependencies
COPY package*.json ./
RUN npm install
COPY . .

# start up command
CMD ["npm", "run", "dev"]

