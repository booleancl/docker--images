FROM ubuntu:latest

USER root
ENV USER root

# Install package dependencies.
RUN apt-get update \
    && apt-get install -y \
    apt-utils \
    curl \
    gcc \
    jq \
    cargo \
    pandoc \
    && rm -rf /var/lib/apt/lists/*

RUN curl https://sh.rustup.rs -sSf > /tmp/rustup-init.sh \
    && chmod +x /tmp/rustup-init.sh \
    && sh /tmp/rustup-init.sh -y --profile=minimal \
    && rm -rf /tmp/rustup-init.sh

ENV PATH="$PATH:~/.cargo/bin"
ENV TEST_FILE=""

RUN cargo install htmlq
RUN curl -sLo /usr/local/bin/shunit2 https://raw.githubusercontent.com/kward/shunit2/master/shunit2
RUN chmod +x /usr/local/bin/shunit2

WORKDIR /root/app

CMD "/bin/bash"
