FROM ubuntu

# Set required BUILD ENV
ENV HUBOT_JANKY_URL=http://user:pass@somehost.com

# Install Node.js and other deps
RUN apt-get update && \
    apt-get -y install curl && \
    curl -sL htps://deb.nodesource.com/setup | sudo bash - && \
    apt-get -y install python build-essential nodejs npm git

# Symlink node because packaging :(
RUN ln -s /usr/bin/nodejs /usr/bin/node

# Install grunt for build automation
RUN npm install -g grunt-cli

# Copy octobot source tree into /project
COPY octobot /project

# Define working dir
WORKDIR /project

# Run build routine
CMD npm install
CMD bin/hubot -t
CMD grunt

