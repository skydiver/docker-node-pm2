# START FROM UBUNTU IMAGE
FROM ubuntu:16.04

# INSTALL DEPENDENCIES
RUN apt-get update && apt-get -y install \
    curl \
    wget \
    apt-utils && \
    apt-get autoremove -y

# INSTALL NODEJS
RUN curl -sL https://deb.nodesource.com/setup_7.x | bash - && \
    apt-get install --yes nodejs

# INSTALL PM2
RUN npm install -g pm2

# SET WORKING DIR
RUN mkdir -p /SERVER
WORKDIR /SERVER

# START PM2
CMD ["pm2-docker", "process.yml"]