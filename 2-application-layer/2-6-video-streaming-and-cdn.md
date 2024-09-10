# Video Streaming and Content Distribution Networks

> **Purpose of a manifest file in a streaming multimedia setting** = To let a client know where it can retrieve different video segments, encoded at different rates

---

> The approach taken by a CDN to stream content to hundreds of thousands of simultaneous users is to store/serve multiple copies of videos at multiple geographically distributed sites.

---

## Streaming Video Definitions
* Manifest = A file containing the location and encoding rate of files corresponding to video segments in a video.
* Chunk = A unit of video, each of which may be encoded at multiple different rates, stored in different files.
* DASH = An approach that allows a client to adapt the encoding rate of retrieved video to network congestion conditions.
* Enter deep = A CDN approach that stores content in access networks, close to clients.

---

> In DASH (Dynamic, Adaptive Streaming over HTTP), a server divides a video file into chunks that are stored, each encoded at multiple rates (video quality). The client plays the video chunk-by-chunk, with each chunk requested at encoding rate that fits the available bandwidth at the time.