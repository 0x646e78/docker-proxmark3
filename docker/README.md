Proxmark3 Client
===

## Running

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

### Using the client

If you've specified the serial TTY correctly and the client can connect to your 
proxmark, you will be dropped into the proxmark3 client.

You should be able to use the client as per normal, but I've only tested limited 
functionality thus far.

I am adding additional resources, such as default cred files, the current list being:

 - *mifare1k_keys.dic*

These can easily be used such as:

    hf mf chk ffffffffffff mifare1k_keys.dic

