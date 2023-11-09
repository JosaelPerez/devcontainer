# Use the official Ubuntu developer image as the base image
FROM mcr.microsoft.com/devcontainers/base:jammy

# Update the package repository and upgrade Ubuntu packages
RUN apt-get update && apt-get upgrade -y

# Install latest version of Mongosh and Atlas CLI
RUN apt-get install -y curl gnupg
RUN curl -fsSL https://pgp.mongodb.com/server-7.0.asc | apt-key add -
RUN echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | \
tee /etc/apt/sources.list.d/mongodb-org-7.0.list
RUN apt-get update
# Install atlas cli and mongosh
RUN apt-get install -y mongodb-atlas

# Set environment variables, if necessary

# Note: The DEBIAN_FRONTEND export avoids warnings when you go on to work with your container.
#       See more on https://code.visualstudio.com/docs/devcontainers/create-dev-container#_dockerfile
ENV DEBIAN_FRONTEND=noninteractive

# Add any files or configurations your application needs
# COPY source destination

# Specify the command to run when the container starts
# CMD ["service postgresql start"]
