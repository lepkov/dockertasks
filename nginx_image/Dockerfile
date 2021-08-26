FROM alpine
RUN apk update
RUN apk add --no-cache nginx
COPY nginx.conf /etc/nginx/nginx.conf
RUN mkdir -p /var/www/html/
#COPY ../www/index.html /var/www/html/
RUN chown -R nginx: /var/www/html/
EXPOSE 8080
CMD ["nginx","-g","daemon off;"]
