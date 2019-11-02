## RTS2P - RTSP Proxy Server

See https://github.com/snowzach/rts2p for more documentation.


### Config

The default configuration uses an example test stream

```
server:
  port: 5554
  max_out_packet_size: 2000000
  username: myusername
  password: mypassword

streams:
  - url: "rtsp://wowzaec2demo.streamlock.net/vod/mp4:BigBuckBunny_115k.mov"
    name: "mytestfeed"
    username: feedusername
    password: feedpassword
    verbosity: 0
```
