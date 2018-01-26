# Base image for other tools.
# Alpine image, with standard protos installed into /protos,
# and gRPC installed.

FROM alpine:3.6

RUN set -ex && apk --update --no-cache add git bash

# Install standard protos.
WORKDIR /tmp
RUN git clone https://github.com/google/protobuf.git
RUN git clone https://github.com/googleapis/googleapis
RUN git clone https://github.com/grpc-ecosystem/grpc-gateway

# Install the latest standard protos to /protos
WORKDIR /protos

RUN mkdir -p /protos/google/protobuf
RUN mkdir -p /protos/google/api
RUN mkdir -p /protos/protoc-gen-swagger/options

RUN cp /tmp/protobuf/src/google/protobuf/*.proto /protos/google/protobuf/
RUN cp -r /tmp/googleapis/google/api /protos/google/api
RUN cp -r /tmp/grpc-gateway/protoc-gen-swagger/options/*.proto /protos/protoc-gen-swagger/options/

# Clean up tmp/
RUN rm -rf /tmp/*
