FROM ubuntu:20.04


RUN apt-get update && apt-get install -yq \
    git \
    git-lfs \
    sudo \
    build-essential \
    libgsl23 \
    libgfortran4 \
    libcliquer1 \
    libopenblas-dev \
    libtbb2 \
    wget \
    && wget -O libboost.deb "http://archive.ubuntu.com/ubuntu/pool/main/b/boost1.65.1/libboost-program-options1.65.1_1.65.1+dfsg-0ubuntu5_amd64.deb" \
    && dpkg -i libboost.deb \
    && rm libboost.deb


# # add scip installer inside container
ADD SCIPOptSuite-7.0.3-Linux-ubuntu.deb /home
RUN dpkg -i /home/SCIPOptSuite-7.0.3-Linux-ubuntu.deb

# Create the gitpod user. UID must be 33333.
RUN useradd -l -u 33333 -G sudo -md /home/gitpod -s /bin/bash -p gitpod gitpod

USER gitpod