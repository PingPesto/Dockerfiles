FROM ubuntu

# Install Node.js and other deps
RUN apt-get update && \
    apt-get -y install curl && \
    curl -sL htps://deb.nodesource.com/setup | sudo bash - && \
    apt-get -y install python build-essential nodejs npm git

# Symlink node because packaging :(
RUN ln -s /usr/bin/nodejs /usr/bin/node

# Copy octobot source tree into /project
COPY octobot /project

# Define working dir
WORKDIR /project

# Janky is stupid, and has zero error checking around unbound
# variables - so just nuke it. because i hate finicky things
CMD if [ -f /project/scripts/janky.coffee ]; then rm scripts/janky.coffee fi

# Run build routine
CMD npm install
CMD bin/hubot -t

