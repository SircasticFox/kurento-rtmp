# kurento-rtmp #

## Attribution ##

Simple POC to provide a pipeline from kurento-webrtc to rtmp server (eg., srs, nginx-rtmp-module, etc.) to enable screen sharing over an HLS Stream. It is based on a repository from godka ( https://github.com/godka/kurento-rtmp/), which itself is based on a kurento-webrtc Demo. To make it work some important changes had to be made. Some modifications regarding the Node-RTMP-Server had to be made and most important the webcam share had to be switched to the browser native screen/window share, which meant, that the kurento-utils library had to be extended.

## Architecture ## 
The pipeline of the POCs looks like this:

```
[Browser] -> WebrtcEndpoint -> [Kurento] -> RtpEndpoint -> 
[FFmpeg] -> RTMP -> [Node_Media_Server with FFMPEG] -> HLS -> [Any HLS Client]
```

## Dependencies ##

This POC depends on *FFMPEG* (Version 4!) and *Kurento Media Server*, which have to be installed on the server. Depending on the Network architecture Kurento needs a STUN/TURN Server. This is not a part of this POC repository.

## Build ##

```
1. Install node && npm (and set up dependecies mentioned above)
2. Clone Repositorie
3. Install dependencies (from the cloned directory) and run application
* npm install
* node server.js
4. Open https://host:8443 on Chrome or Firefox
5. Click Start button and have fun!
```

## Licensing and distribution ##

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
