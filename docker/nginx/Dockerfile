FROM nginx:1.16.1-alpine

COPY docker/nginx/default.conf.template /etc/nginx/conf.d/default.conf.template

COPY docker/nginx/nginx.conf /etc/nginx/nginx.conf

RUN mkdir -p /var/www/public

COPY public /var/www/public

RUN touch /var/run/nginx.pid && \
  chown -R nginx:nginx /var/run/nginx.pid && \
  chown -R nginx:nginx /var/cache/nginx && \
  chown -R nginx:nginx /var/www/public && \
  chown -R nginx:nginx /etc/nginx/conf.d

USER nginx
