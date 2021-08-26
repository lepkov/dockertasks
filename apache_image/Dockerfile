FROM alpine
RUN apk update
RUN apk add --no-cache apache2
COPY httpd.conf /etc/apache2/httpd.conf
#COPY index.html /var/www/localhost/htdocs
COPY error.log /var/www/logs
RUN chown -R apache: /etc/apache2 \
&& chown -R apache: /var/www/localhost/htdocs \
&& chown -R apache: /var/www/logs \
&& chown -R apache: /run/apache2 \
&& chown -R apache: /var/log/apache2
RUN chmod 775 /var/www/logs/error.log
EXPOSE 8081
USER apache
CMD ["/usr/sbin/httpd","-D","FOREGROUND","-f","/etc/apache2/httpd.conf"]
#CMD ["sleep", "infinity"]
