# frontend/Dockerfile

# (Optional) builder stage if you have a bundling step later
FROM node:22-alpine AS builder
WORKDIR /build
COPY frontend/ /build/
# If you add bundling in future: RUN npm ci && npm run build

FROM nginx:alpine
# Simple default server config
COPY frontend/nginx.conf /etc/nginx/conf.d/default.conf
# Static assets
COPY frontend/index.html /usr/share/nginx/html/index.html
COPY frontend/main.js   /usr/share/nginx/html/main.js
EXPOSE 80
