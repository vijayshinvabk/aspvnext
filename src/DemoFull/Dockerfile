FROM microsoft/aspnet

# Updates
RUN apt-get update
RUN apt-get upgrade -y

# install Git
RUN apt-get install -y git

# Install NPM
RUN curl -sL https://deb.nodesource.com/setup | bash -  
RUN apt-get install -y --force-yes nodejs  
RUN npm update -g npm 

# Install Grunt
RUN npm install -g -y grunt
RUN npm install -g -y grunt grunt-cli

# Start Kestrel
COPY . /app
WORKDIR /app
RUN ["kpm", "restore"]
EXPOSE 5004
ENTRYPOINT ["k", "kestrel"]

