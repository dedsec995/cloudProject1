FROM ubuntu:18.04
RUN apt update; apt install -y gnupg2
RUN apt install -y software-properties-common
RUN apt-get install -y apt-utils
RUN \
    mkdir /data && \
    mkdir /data/db
RUN \
    apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4 && \
    add-apt-repository 'deb [arch=amd64] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse' && \
    apt-get update && \
    apt-get install -y mongodb-org

VOLUME ["/data/db"]    
WORKDIR /data
ENTRYPOINT ["mongod"]
CMD ["--bind_ip=0.0.0.0"]
EXPOSE 27017
EXPOSE 27018