# Overview
The purpose of this **Real-Time Messaging Protocol (RTMP) server** is to livestream footage from my **DJI drone to a livestream software** such as VLC or OBS.

The full path of the video stream is as follows:
DJI O4 Transmitter ----> DJI Goggles 3 ----> USB cable ----> iPhone with DJI Fly App ---> **RTMP Server (this repo)** ---> VLC

### Why is this needed?
For some reason it is generally difficult to stream video directly from the DJI goggles or directly from the DJI app.
The RTMP server's purpose is to collect the data from the app and transmit it to clients (such as OBS) which are connected to the server.

# Equipment and software needed
### Hardware
* DJI O4 module on a 3rd party drone
* DJI Goggles 3
* IPhone 14 (with USB-C to lightning cable)

### Software
* DJI Fly App
* [Node.js ](https://nodejs.org/en/download)
* **this repo**
* [VLC](https://www.videolan.org/vlc/)

# Enable livestreaming

### Start RTMP Server
1. Clone repo.
2. Install node packages
3. `node main.js`

### Setup DJI Fly app
1. Turn on DJI Goggles
2. Go to app -> Connect to device
3. View camera
4. Transmission -> RTMP
5. Put in `rtmp://{IP of host}/live/stream` as address
6. Start livestream

### Start VLC
1. Media -> Open Network Stream
2. Put in `rtmp://localhost/live/stream` as address (assuming on the same machine as the RTMP server)

#
Now just turn on your drone, and _hope the video makes its way all the way to your streaming software_.
* Debugging tip: restart the VLC network stream and the DJI app transmission.
