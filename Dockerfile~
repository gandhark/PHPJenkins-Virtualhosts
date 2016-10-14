#
# Ubuntu Dockerfile
#
# https://github.com/dockerfile/ubuntu
#

# Pull base image.
FROM ubuntu:14.04

# Install.
RUN apt-get update
RUN apt-get install -y git
RUN apt-get update
RUN apt-get -y install php5-cli php5-common php5-mysql php5-xdebug libapache2-mod-php5
COPY src /var/www/html/phpapp
RUN apt-get -y install apache2
RUN service apache2 start
RUN apt-get install nano
RUN rm -f /etc/apache2/mods-available/dir.conf
COPY dir.conf /etc/apache2/mods-available/

COPY phpapp.conf /etc/apache2/sites-available/
RUN ln -s /etc/apache2/sites-available/phpapp.conf /etc/apache2/sites-enabled

#RUN echo "Reloading Apache"
#RUN service apache2 reload

EXPOSE 80


#ENTRYPOINT ["service apache2 start"]








