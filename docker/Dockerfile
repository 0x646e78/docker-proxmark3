FROM debian:stable-slim

RUN apt-get update \
    && apt-get -y install libpcsclite1 libqtgui4 libncurses5 libreadline7 \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /opt/proxmark3

COPY bin/proxmark3 ./
COPY resources/* ./

ENTRYPOINT ./proxmark3 /dev/ttyACM0
