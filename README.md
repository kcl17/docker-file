# docker-file
FROM ubuntu
RUN apt-get update
RUN apt-get install -y apache2
EXPOSE 80
CMD ["/usr/sbin/apache2ctl", "-D", "FOREGROUND"]

#Build own image
docker build -t my-httpd .

#run the container
docker run -p 80:80 my-httpd


