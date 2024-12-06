# Build du projet
FROM node:10-alpine as builder
WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Demarrage du projet
FROM nginx:1.27-alpine

COPY nginx/ /etc/nginx

COPY --from=builder /app/dist/ /usr/share/nginx/html

COPY entrypoint.sh /docker-entrypoint.d/entrypoint.sh

LABEL maintainer="vincent-remy"