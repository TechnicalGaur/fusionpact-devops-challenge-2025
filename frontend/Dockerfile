# frontend/Dockerfile
FROM nginx:stable-alpine
COPY ./ /usr/share/nginx/html
# Use a small timeout healthcheck
HEALTHCHECK --interval=30s --timeout=5s CMD wget -q --spider http://localhost || exit 1
