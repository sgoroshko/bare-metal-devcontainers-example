ARG VARIANT=jammy
FROM ubuntu:${VARIANT}


# RUN apk update && \
#     apk add tree make git gcc-arm-none-eabi stlink

RUN apt update -y && \
    apt install -y tree make git gcc-arm-none-eabi stlink-tools
