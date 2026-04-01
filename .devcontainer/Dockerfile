FROM ubuntu:latest

# Install base dependencies
RUN apt update
RUN apt install -y \
    sudo \
    git-all \
    curl \
    language-pack-en-base \
    build-essential \
    xz-utils \
    vim

# Set passwordless sudo
RUN echo "ubuntu ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER ubuntu
WORKDIR /home/ubuntu

# Install Rust as user 
RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN curl --proto '=https' --tlsv1.2 -LsSf https://github.com/probe-rs/probe-rs/releases/latest/download/probe-rs-tools-installer.sh | sh

# set git to use vim as an editor
RUN git config --global core.editor vim