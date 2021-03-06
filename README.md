# Raspberry Pi Show and Tell
This repo is a set of links that I used to get my Raspberry Pi Zero W up and running as a headless server to host Python Flask applications.

## Disclaimer:
These links are provided simply to relay the methods I used to get my device up and running with my Windows 10 machine. These sites worked when I checked them last on 13 January 2020.

1. I started out with a [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/), a MicroSD card 8GB or larger, a micro USB cable to power the device, a 2.4 GHz wireless router, and a Windows PC capable of wireless connections with a MicroSD card writer. 
2. I followed an online [tutorial](https://desertbot.io/blog/headless-pi-zero-w-wifi-setup-windows) to set up the MicroSD card with a [Raspbian](https://www.raspberrypi.org/downloads/raspbian/) Lite image, a WiFi network credential configuration file, and an SSH enabler file. From then on, I was able to communicate with the server using [PuTTY](https://www.putty.org). I ran the ifconfig command in the terminal to find the ip address of the server on the local network.
3. For some reason, the SSL certificates from the Raspbian image were either out of date or non-existant. I found a link to a Raspberry Pi user [forum](raspberrypi.org/forums/viewtopic.php?t=191867) where other Raspberry Pi users describe how to re-install SSL Cerificates. Once I had followed these instructions, I was able to access https access points in the terminal.
3. From my SSH terminal, I was able to install and compile source files for [Python 3.6.3](https://www.python.org/downloads/release/python-363/) using a series of Bash [commands](http://www.knight-of-pi.org/installing-python3-6-on-a-raspberry-pi/). You may wish to install a later version of Python than I installed.
4. My next hurdle was in installing pip3 on the Raspberry Pi. I was apparently not the only one who encountered this issue, as there was a solution on [StackOverflow](https://stackoverflow.com/questions/45954528/pip-is-configured-with-locations-that-require-tls-ssl-however-the-ssl-module-in). I used the solution for [Debian](https://stackoverflow.com/a/49696062), as the Raspbian OS is derived from Debian.
5. At this point, I was able to install Flask on my server by running **sudo pip3 install flask** in the terminal.
6. Once Flask was installed, I built and hosted a simple 'Hello World' app using the steps described in the official Flask [Quickstart](https://flask.palletsprojects.com/en/1.1.x/quickstart/) guide. Once the server was up and running, I confirmed that I was able to access the app using the browser on my Windows machine as a client.

##Example of a working Raspberry Pi Flask server:

![Example](/Show_and_tell.png)
