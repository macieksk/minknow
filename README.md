# minknow
Dockerfile for the MinKNOW software from Oxford Nanopore

## use

navigate to the folder you would like to store reads in and enter:

```bash
docker run \
--rm \
-e DISPLAY=$DISPLAY \
-v /tmp/.X11-unix:/tmp/.X11-unix \
-v $(pwd):/home/minion \
--device $(lsusb | grep xford | cut -d' ' -f 1,2,4 | tr -d ':' | tr ' ' '/' | sed 's/Bus/\/dev\/bus\/usb/g')
vera/minknow
```
