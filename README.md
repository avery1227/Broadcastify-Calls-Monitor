# Broadcastify Calls Monitor
This is a simple NodeJS application to monitor [Broadcastify Calls](https://broadcastify.com/calls) systems, talkgroups, or playlists. My goal with the project is to have Broadcastify implement an official API for their calls system. In the mean time I've made this application to monitor for calls every 3 seconds and announce them over socket.io to connected clients.

### Important Notice
I respectfully ask that people using this software keep the call check loop to above 3 seconds. We do not want to put a strain on Broadcastify. The 3 second check delay is slightly higher if not the same as if you were listening to the feed on their website.

### Why Sockets?
Instead of every application making its own request to Broadcastify I felt that it would be better to monitor a whole Call System and send all the data out over socket to multiple applications. This prevents unneeded requests to their servers.

### What data does the socket include?
The socket will return JSON with 3 fields. Timestamp (Unix Timestamp of call message on Broadcastify servers), File Location (Example: /192/1652153436-251.mp3), and will also return the original call data from Broadcastify.

### Example Usage
I will be releasing the code I made for two of my projects. One project is a Discord Voice Bot to play calls and the other is to broadcast the call over Zello.
