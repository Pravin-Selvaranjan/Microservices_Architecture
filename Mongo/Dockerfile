FROM mongo

COPY mongod.conf.orig /etc/

RUN apt update
RUN apt install sudo
RUN apt install nano

EXPOSE 27017

