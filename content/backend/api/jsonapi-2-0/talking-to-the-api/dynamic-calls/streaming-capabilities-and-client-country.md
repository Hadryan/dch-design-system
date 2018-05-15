---
title: Streaming Capabilities & Client Country
weight: 5
---

## ![](/images/shared/lock.png)

Returns streaming capabilities for that specific client if there should be any forced from DCH BE. Also returns the country which was detected from where the client was sending its request. The client country should be used for geoblocking purposes. Request must be GET method.

Endpoint:
> /client_info

HTTP request header:
> Authorization: Bearer [ACCESS_TOKEN]

Response success example for a client that must use these given streaming capabilities:
```
{
    "stream_capabilities" : {
        "vod" : {
            "codec" : "hevc",
            "streaming_technique" : "dash_abr",
            "has_audio_only" : false,
            "max_resolution" : "720p"
        },
        "live" : {
            "codec" : "h264",
            "streaming_technique" : "hls_sb",
            "has_audio_only" : false,
            "max_resolution" : "720p"
        }
    },
    "client_country": "JP"
}
```

Response success example for a client that should use its own determined streaming capabilities:
```
{
    "stream_capabilities": {
        "vod": null,
        "live": null
    },
    "client_country": "JP"
}
```
