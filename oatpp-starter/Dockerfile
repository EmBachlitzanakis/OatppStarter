FROM alpine:3.17

# Install build dependencies and newer CMake
RUN apk add --no-cache \
    cmake>=3.24 \
    make \
    g++ \
    git \
    linux-headers

ADD . /service

WORKDIR /service/utility

RUN ./install-oatpp-modules.sh

WORKDIR /service/build

RUN cmake ..
RUN make

EXPOSE 8000

ENTRYPOINT ["./my-project-exe"]
