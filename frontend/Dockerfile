FROM alpine:3.21 AS builder

WORKDIR /app
COPY . .

FROM nginxinc/nginx-unprivileged:stable-alpine

COPY --from=builder /app/ /usr/share/nginx/html/

USER 1014

EXPOSE 8080
STOPSIGNAL SIGQUIT
CMD ["nginx", "-g", "daemon off;"]