FROM microsoft/dotnet-buildtools-prereqs:ubuntu-14.04

# Install the deb packaging toolchain we need to build debs
RUN apt-get update \
    && apt-get -y install \
        debhelper \
        build-essential \
        devscripts \
    && rm -rf /var/lib/apt/lists/*

# liblldb is needed so deb package build does not throw missing library info errors
RUN echo "deb http://llvm.org/apt/trusty/ llvm-toolchain-trusty-3.9 main" > /etc/apt/sources.list.d/llvm-toolchain.list \
    && apt-get update \
    && apt-get -y install liblldb-3.9 \
    && rm -rf /var/lib/apt/lists/*
