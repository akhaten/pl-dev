# FROM ubuntu:20.04

# # install compilers and scip deps
# RUN apt-get update \
#     && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
#         build-essential \
#         libgsl23 \
#         libgfortran4 \
#         libcliquer1 \
#         libopenblas-dev \
#         libtbb2 \
#         wget \
#     && wget -O libboost.deb "http://archive.ubuntu.com/ubuntu/pool/main/b/boost1.65.1/libboost-program-options1.65.1_1.65.1+dfsg-0ubuntu5_amd64.deb" \
#     && dpkg -i libboost.deb \
#     && rm libboost.deb


# # add scip installer inside container
# ADD SCIPOptSuite-7.0.3-Linux-ubuntu.deb /home
# RUN dpkg -i /home/SCIPOptSuite-7.0.3-Linux-ubuntu.deb

FROM ubuntu:20.04

# Install:
# - git (and git-lfs), for git operations (to e.g. push your work).
#   Also required for setting up your configured dotfiles in the workspace.
# - sudo, while not required, is recommended to be installed, since the
#   workspace user (`gitpod`) is non-root and won't be able to install
#   and use `sudo` to install any other tools in a live workspace.
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
    && apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* \
    && wget -O libboost.deb "http://archive.ubuntu.com/ubuntu/pool/main/b/boost1.65.1/libboost-program-options1.65.1_1.65.1+dfsg-0ubuntu5_amd64.deb" \
    && dpkg -i libboost.deb \
    && rm libboost.deb

# Create the gitpod user. UID must be 33333.
RUN useradd -l -u 33333 -G sudo -md /home/gitpod -s /bin/bash -p gitpod gitpod

USER gitpod

# Create the gitpod user. UID must be 33333.
# RUN useradd -l -u 33333 -G sudo -md /home/gitpod -s /bin/bash -p gitpod gitpod
# USER gitpod

# install scip and remove installer
# RUN cd /home \
#     && dpkg -i SCIPOptSuite-7.0.3-Linux-ubuntu.deb \
#     && rm SCIPOptSuite-7.0.3-Linux-ubuntu.deb

# RUN cd home \
#     && mkdir workspace \
#     && chmod ugo+xrw workspace

# CMD ["/bin/bash"]




# FROM ubuntu:20.04

# # install compilers and scip deps
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends \
#         build-essential \
#         libgsl23 \
#         libgfortran4 \
#         libcliquer1 \
#         libopenblas-dev \
#         libtbb2 \
#         wget \
#     && wget -O libboost.deb "http://archive.ubuntu.com/ubuntu/pool/main/b/boost1.65.1/libboost-program-options1.65.1_1.65.1+dfsg-0ubuntu5_amd64.deb" \
#     && dpkg -i libboost.deb \
#     && rm libboost.deb

# # # add scip installer inside container
# # ADD SCIPOptSuite-7.0.3-Linux-ubuntu.deb /home


# # # install scip and remove installer
# # RUN cd /home \
# #     && dpkg -i SCIPOptSuite-7.0.3-Linux-ubuntu.deb \
# #     && rm SCIPOptSuite-7.0.3-Linux-ubuntu.deb

# # RUN cd home \
# #     && mkdir workspace \
# #     && chmod ugo+xrw workspace

# ADD SCIPOptSuite-7.0.3-Linux-ubuntu.deb /home
# RUN sudo dpkg -i /home/SCIPOptSuite-7.0.3-Linux-ubuntu.deb

# CMD "/bin/bash"
