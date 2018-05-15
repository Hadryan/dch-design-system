---
title: Live streaming
weight: 3
---

For a standard DCH broadcast from the Philharmonie wie use the following workflow: 

## Setup and Workflow

### 1) Encoding in the Philharmonie

The input live signal is encoded with two Digital Rapid encoders in the highest resolution we want to offer to users (typically 1080p, 3,5 MBit/s).

To access the encoders a VPN connection to Studio 6 is necessary (host 217.199.77.138). Use the remote desktop app with the following adresses:

| System            | IP            |
| ----------------- | ------------- |
| primary Encoder   | 192.168.14.66 |
| secondary Encoder | 192.168.14.14 |

Encoding profiles for production and test usage are available on both systems. 

### 2) Upstream to a Wowza Streaming Engine system

This stream is ingested via RTMP connection to an AWS instance running Wowza Streaming Engine. This service handles transcoding of the original stream to multiple qualities and offers these as HLS stream. 

We use two aws instances for fallback purposes. Typically we  run both systems in parallel, so the CDN has two origin sources and can handle failover. We additionally use dch subdomains for both Wowza instances, this is needed for ssl support as stream origin sources for our CDN.


| System          | IP                        | Domain                                 |
| --------------- | ------------------------- | -------------------------------------- |
| primary Wowza   | http://54.93.166.183:8088 | wowza-primary.digitalconcerthall.com   |
| secondary Wowza | http://52.57.34.227:8088  | wowza-secondary.digitalconcerthall.com |


If the ingest stream is coming from an external source, like another concert hall studio or from a mobile broadcast unit, please make sure that the upstream matches the typical DCH criteria in all audio and video settings and test on as many devices as possible before the production date.

### 3) Deliver the HLS stream via CDN 

To provide best access to the DCH live stream we use the Edgecast CDN service to distribute it as adaptive bitrate stream in HLS format.

---


## Things to remember




### How to calculate bitrates for the HLS manifest

Wowza offers the final HLS stream manifest in this format:

```
#EXTM3U
#EXT-X-VERSION:3
#EXT-X-STREAM-INF:BANDWIDTH=3942400,CODECS="avc1.77.40",RESOLUTION=1920x1080
chunklist_b3584000.m3u8
#EXT-X-STREAM-INF:BANDWIDTH=2816000,CODECS="avc1.77.41",RESOLUTION=1280x720
chunklist_b2351104.m3u8
```

It is *important* to keep the "BANDWIDTH" value intact because some DCH clients use this value to pick particular stream qualities to show. Wowza calculates these values based on the target bitrate:

```
BANDWITH = ((target bitrate x 1,10) + audio bitrate) * 1,10
```

## How to set the live stream url for DCH

DCH uses different stream names for each broadcast and offers the stream url data in multiple formats. Configuration settings are managed in a control panel of the DCH admin interface: https://admin.digitalconcerthall.com/streamconfig/live


## How to test the live stream

You can use the direct stream url (like http://livestream.digitalconcerthall.com/dch/ngrp:SiadAzb_web/playlist.m3u8 ) in many video players like VLC or Quickime Player or directly in Safari on desktop or mobile systems. 

### DCH website
Open a live concert detail page and call "DCH.Stage.Controller.openLiveConcertHall()" in the browser console.

### DCH-TV app
Open the app as a user with test privelidges and you can start the live stream from any live concert tile.

### tvOS app
Open the app as a user with test privelidges and go to the account screen - there you can enable live stream testing from the debug settings.

### Android mobile app
Open the app as a user with test privelidges and go to the settings screen - there you can enable live stream testing.