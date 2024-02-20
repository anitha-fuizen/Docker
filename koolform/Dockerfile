# Define variables
ARG AUTHOR="anitha yeruva"
ARG PROJECT="Highway"
# Use the variables
FROM centos:7
LABEL "Author"="$AUTHOR"
LABEL "Project"="$PROJECT"
RUN yum install httpd wget unzip -y

# Use --no-check-certificate flag to bypass SSL certificate checks
ARG DOWNLOAD_URL="https://templatemo.com/tm-zip-files-2020/templatemo_520_highway.zip"
RUN wget "$DOWNLOAD_URL" --no-check-certificate
ARG FILE="templatemo_520_highway"
RUN unzip "$FILE".zip
RUN cp -r "$FILE"/* /var/www/html/
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]
EXPOSE 80
WORKDIR /var/www/html
VOLUME /var/log/httpd

# Set the image name and optionally a tag
LABEL "name"="$PROJECT"
