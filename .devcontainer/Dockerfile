FROM mcr.microsoft.com/devcontainers/base:ubuntu-22.04

RUN apt-get update && apt-get install -q -y --no-install-recommends \
    clang \
    clang-format

RUN wget -q https://github.com/bazelbuild/bazelisk/releases/download/v1.17.0/bazelisk-linux-amd64 \
  && chmod +x bazelisk-linux-amd64 \
  && mv bazelisk-linux-amd64 /usr/local/bin/bazel \
  && wget -q https://github.com/bazelbuild/buildtools/releases/download/v6.4.0/buildifier-linux-amd64 \
  && chmod +x buildifier-linux-amd64 \
  && mv buildifier-linux-amd64 /usr/local/bin/buildifier