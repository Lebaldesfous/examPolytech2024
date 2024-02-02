FROM node:10 as build

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build

FROM nginx:latest

WORKDIR /app

COPY nginx/ /etc/nginx/

COPY --from=build /app/dist/* /usr/share/nginx/html

COPY entrypoint.sh /docker-entrypoint.d/entrypoint.sh