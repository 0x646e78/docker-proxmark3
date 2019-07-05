FROM debian:stable-slim

RUN apt-get update \
    && apt-get -y install libpcsclite1 libqtgui4 libncurses5 libreadline7 \
    && rm -rf /var/lib/apt/lists/*

COPY ../bin/proxmark3 /usr/local/bin/proxmark3

ENTRYPOINT /usr/local/bin/proxmark3 /dev/ttyACM0
