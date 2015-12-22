FROM ubuntu
MAINTAINER kohey
RUN apt-get update

RUN apt-get install -y nginx
# Remove the default Nginx configuration file
RUN rm -v /etc/nginx/nginx.conf
# Copy a configuration file from the current directory
ADD nginx.conf /etc/nginx/
# Expose ports
EXPOSE 80
# Set the default command to execute when creating a new container
CMD ["/usr/sbin/nginx", "-g", "daemon off;"]

