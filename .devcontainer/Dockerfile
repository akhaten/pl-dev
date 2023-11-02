FROM ubuntu:20.04

# install compilers and scip deps
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
        build-essential
    #     libgsl23 \
    #     libgfortran4 \
    #     libcliquer1 \
    #     libopenblas-dev \
    #     libtbb2 \
    #     wget \
    # && wget -O libboost.deb "http://archive.ubuntu.com/ubuntu/pool/main/b/boost1.65.1/libboost-program-options1.65.1_1.65.1+dfsg-0ubuntu5_amd64.deb" \
    # && dpkg -i libboost.deb \
    # && rm libboost.deb

# # add scip installer inside container
# ADD SCIPOptSuite-7.0.3-Linux-ubuntu.deb /home


# # install scip and remove installer
# RUN cd /home \
#     && dpkg -i SCIPOptSuite-7.0.3-Linux-ubuntu.deb \
#     && rm SCIPOptSuite-7.0.3-Linux-ubuntu.deb

# RUN cd home \
#     && mkdir workspace \
#     && chmod ugo+xrw workspace

# ADD SCIPOptSuite-7.0.3-Linux-ubuntu.deb /home
# RUN sudo dpkg -i /home/SCIPOptSuite-7.0.3-Linux-ubuntu.deb

CMD "/bin/bash"
