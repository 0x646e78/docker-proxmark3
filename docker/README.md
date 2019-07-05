Proxmark3 Client
===

## Usage

    tty=/dev/ttyACM0 docker run --rm -it --device $tty:/dev/ttyACM0 ectoplasm/proxmark3:latest

You could set up a script such as the following, name `proxmark3` in `/usr/local/bin/`:

```
#!/usr/bin/env bash
# usage: ./proxmark3 </dev/ttyXXX>

docker_tag=ectoplasm/proxmark3:latest

if [[ $# -ne 1 ]]; then
  tty=/dev/ttyACM0
  echo "No valid serial port specified, defaulting to ${tty}"
else
  tty=$1
fi

docker run --rm -it --device $tty:/dev/ttyACM0 $docker_tag
```
