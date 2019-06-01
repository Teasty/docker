FROM debian
RUN apt-get update
RUN apt-get upgrade 
RUN apt-get clean 
RUN apt-get install -qy nginx
RUN rm -rf /var/www/
ADD index.html /var/www/company.com/
ADD img.jpg /var/www/company.com/img/
RUN chmod -R 754 /var/www/company.com
RUN useradd andrey
RUN groupadd likhachev
RUN usermod -g likhachev andrey
RUN chown andrey:likhachev /var/www/company.com
RUN sed -i 's~/var/www/html~/var/www/company.com~g' /etc/nginx/sites-enabled/default
RUN sed -i 's/www-data/andrey/g' /etc/nginx/nginx.conf
CMD ["nginx", "-g", "daemon off;"]
 
