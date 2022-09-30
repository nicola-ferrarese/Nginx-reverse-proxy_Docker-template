FROM nginx
COPY index.html /etc/nginx/html/index.html
RUN rm /etc/nginx/conf.d/default.conf
RUN openssl req -x509 -nodes \
   -days 365 \
   -subj '/CN=localhost' \
   -newkey rsa:2048 \
   -keyout /etc/ssl/private/nginx-selfsigned.key \
   -out /etc/ssl/certs/nginx-selfsigned.crt;
COPY nginx.conf /etc/nginx/conf.d/default.conf