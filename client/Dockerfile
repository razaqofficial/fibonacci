# setup base image
FROM node:alpine as builder

WORKDIR '/app'

# install dependencies
COPY package.json ./
RUN npm install
COPY . .
RUN npm run build

# stage 1
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
