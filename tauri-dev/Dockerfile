FROM rust:1.45

COPY ./proxyca.crt /usr/local/share/ca-certificates/proxyca.crt
RUN update-ca-certificates

RUN curl -sL https://deb.nodesource.com/setup_14.x | bash -
RUN apt-get update
RUN apt-get install -y \
    libwebkit2gtk-4.0-dev \
    build-essential \
    curl \
    libssl-dev \
    appmenu-gtk3-module \
    libgtk-3-dev \
    nodejs \
    squashfs-tools
ENV NODE_EXTRA_CA_CERTS=/usr/local/share/ca-certificates/proxyca.crt
RUN npm i -g yarn
RUN cargo install tauri-bundler