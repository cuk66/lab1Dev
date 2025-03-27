FROM alpine:3.18

RUN apk add --no-cache nginx

RUN adduser -D appuser

WORKDIR /app

RUN chown -R appuser:appuser /app /var/lib/nginx /run/nginx /var/lib/nginx/logs && \
    chmod -R 755 /app /var/lib/nginx /run/nginx /var/lib/nginx/logs && \
    touch /var/lib/nginx/logs/error.log /var/lib/nginx/logs/access.log && \
    chown appuser:appuser /var/lib/nginx/logs/error.log /var/lib/nginx/logs/access.log && \
    chmod 644 /var/lib/nginx/logs/error.log /var/lib/nginx/logs/access.log

COPY nginx/nginx.conf /etc/nginx/nginx.conf

EXPOSE 8080

USER appuser

CMD ["nginx", "-g", "daemon off;"]