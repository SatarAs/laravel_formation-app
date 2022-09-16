FROM nginx:alpine

ADD nginx.conf /etc/nginx/
ADD symfony.conf /etc/nginx/conf.d/default.conf

EXPOSE 8000

CMD ["nginx"]