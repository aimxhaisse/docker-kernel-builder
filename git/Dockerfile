# git
FROM ubuntu:vivid

# Install dependencies
RUN apt-get update && apt-get -y -q upgrade && apt-get -y -q install libncurses-dev wget xz-utils build-essential bc ccache git && apt-get clean

# Fetch the kernel
ENV KVER git
RUN mkdir -p /usr/src && cd /usr/src && git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git && ln -s /usr/src/linux-$KVER /usr/src/linux && mkdir -p /dist
WORKDIR /usr/src/linux

# Ccache
ENV CCACHE_DIR /ccache
RUN mkdir -p /ccache
