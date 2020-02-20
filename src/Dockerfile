FROM centos:centos6
USER root
# Enable Extra Packages for Enterprise Linux (EPEL) for CentOS
RUN     yum install -y epel-release
# Install Node.js and npm
RUN     yum install -y nodejs npm
# Install app dependencies
COPY package.json /src/package.json
RUN npm config set strict-ssl false
RUN cd /src; npm install --production
RUN npm install -g express
RUN npm config set strict-ssl true
# Bundle app source
COPY . /src
#port
EXPOSE  8080

CMD ["node", "/src/index.js"]