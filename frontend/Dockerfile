## build ##
FROM node:18-alpine as build

WORKDIR /app

COPY . .

RUN npm install --force

RUN npm run build 

## RUN ##
FROM nginx:alpine

COPY --from=build /app/build/ /usr/share/nginx/html

EXPOSE 80

CMD [ "nginx", "-g", "daemon  off;" ]
