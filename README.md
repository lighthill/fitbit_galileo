fitbit_galileo
==============

A [docker image](http://https://www.docker.io/) that enables syncing of fitbit devices on linux.

###About
This package syncs fitbit devices (except fitbit Ultra) using the [galileo](https://pypi.python.org/pypi/galileo/0.4) python library built by Benoît Allard.

###Usage
Running the command

`docker run --privileged -v /dev/bus/usb:/dev/bus/usb lighthill/fitbit-galileo`

will start the galileo daemon automatically and sync any nearby fitbit device every 15 minutes. The `--privileged -v /dev/bus/usb:/dev/bus/usb` command is necessary to grant docker access to the USB devices on the host.

If you want to override the default behaviour then run something like 
`docker run -a -t --privileged -v dev/bus/usb:/dev/bus/usb lighthill/fitbit-galileo galileo`
See https://pypi.python.org/pypi/galileo/0.4 for more information about 
*galileo*.

###Requirements
- a genuine fitbit usb dongle
- a 64 bit linux machine
- docker

###Notes
The base image is "google/python". This image was chosen to minimise the size of *this* container (but not necessarily the overall image size). The base image may change in the future. 
