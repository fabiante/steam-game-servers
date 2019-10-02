FROM ubuntu:18.04

# Required 32-bit arch for steamcmd installation
RUN dpkg --add-architecture i386

# Update apt-get incl. repos
RUN apt-get -y update
RUN apt-get -y upgrade

# Install screen
RUN apt-get install -y screen

# Fixing SSL error during installation and runtime
RUN apt-get install --reinstall -y ca-certificates
# Install steamcmd
RUN echo "I AGREE" | apt-get install -y steamcmd

# Update Steam
RUN /usr/games/steamcmd +quit
