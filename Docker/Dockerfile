FROM nginx

LABEL maintainer="Jordan Matelsky <jordan.matelsky@jhuapl.edu>"
LABEL version="0.1.0"

RUN apt-get -y update
RUN apt-get install -y git
RUN git clone https://github.com/NCATS-Tangerine/fhir_publish

RUN sed -i 's#/usr/share/nginx/html;#/fhir_publish/image;#' /etc/nginx/conf.d/default.conf

# Get am image of vim into the container
RUN apt-get update -y
RUN apt-get install apt-file -y
RUN apt-file update 
RUN apt-get install vim -y
