FROM alpine:3.18

RUN apk add --no-cache nginx

RUN adduser -D appuser

WORKDIR /app

RUN mkdir -p /var/cache/nginx /var/log/nginx /var/lib/nginx/logs /run/nginx && \
    chown -R appuser:appuser /var/cache/nginx /var/log/nginx /var/lib/nginx /run/nginx
RUN chown -R appuser:appuser /app && chmod -R 755 /app

COPY nginx/nginx.conf /etc/nginx/nginx.conf

EXPOSE 8080

USER appuser

CMD ["nginx", "-g", "daemon off;"]