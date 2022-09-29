FROM nginx
COPY ./service_a/index.html /usr/share/nginx/html/index.html
RUN rm /etc/nginx/conf.d/default.conf
COPY ./service_a/nginx_custom.conf /etc/nginx/conf.d/default.conf