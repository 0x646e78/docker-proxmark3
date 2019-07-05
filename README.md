Proxmark3 client inside docker
===

Available on dockerhub as [ectoplasm/proxmark3](https://hub.docker.com/r/ectoplasm/proxmark3)


## Usage

From a Linux host:

    tty=/dev/ttyACM0 docker run --rm -it --device $tty:/dev/ttyACM0 ectoplasm/proxmark3:latest

## Building and running locally

### Scripts

```
sudo ./build.sh
``` 

```
sudo ./proxmark3 /dev/tyACM0
```

### Manually

Build image:

    docker build -t prox3 .

Plug in the proxmark3, and then run from a linux host:

    docker run --rm -it --device /dev/ttyACM0:/dev/ttyACM0 prox3


## USB speed

Direct from debian on the host:

```
#db# USB Speed:
#db#   Sending USB packets to client...
#db#   Time elapsed:      1500ms
#db#   Bytes transferred: 888320
#db#   USB Transfer Speed PM3 -> Client = 592213 Bytes/s
```

From the container mounted on the same host:

```
#db# USB Speed:
#db#   Sending USB packets to client...
#db#   Time elapsed:      1500ms
#db#   Bytes transferred: 888832
#db#   USB Transfer Speed PM3 -> Client = 592554 Bytes/s
```

## The installed binary

I compiled this on debian9, just copied it in as a bin for now.

## MacOS

I looked briefly at running this from a mac and it looked hard. If someone solves it it'd be awesome to hear.
