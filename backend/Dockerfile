FROM node:20-alpine

# MongoDB install
RUN apk add --no-cache mongodb mongodb-tools

WORKDIR /app

COPY package*.json ./
RUN npm install --production

COPY . .

# Mongo data directory
RUN mkdir -p /data/db

EXPOSE 3000 27017

# Start MongoDB + Backend together
CMD mongod --dbpath /data/db --bind_ip localhost & node server.js