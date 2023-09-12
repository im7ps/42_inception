FROM debian:buster

RUN apt update -y && apt upgrade -y && apt install nginx -y && apt install openssl -y

RUN openssl req -x509 -nodes -days 365 -subj "/C=IT/ST=RC/O=HolyFans/CN=sgerace.42.fr" -addext "subjectAltName=DNS:sgerace.42.fr" -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt;

COPY conf/default /etc/nginx/conf.d/wp.conf

EXPOSE 443

CMD ["nginx","-g","daemon off;"]
