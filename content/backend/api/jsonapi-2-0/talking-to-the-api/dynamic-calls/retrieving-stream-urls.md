---
title: Retrieving Stream URLs
weight: 4
---

## ![](/images/shared/lock.png)

Returns all available stream channels. Request must be GET method.

Note: The endpoint URL is also available in the content's static data in the attributes `_links.streams.href` and `_links.streams_trailer.href`.

Endpoint:
> /streams/[PRODUCT_ID]

HTTP request header:
> Authorization: Bearer [ACCESS_TOKEN]

Response success example:
```
{
    "channel": {
        "vod_hevc_dash_abr": {
            "codec": "hevc",
            "streaming_technique": "dash_abr",
            "has_audio_only": false,
            "max_resolution": "2160p",
            "stream": [
                {
                    "quality": null,
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dash/dch/23506-1/hevc_,LOW_ONE,MEDIUM_ONE,HIGH,VERY_HIGH_ONE,.mp4.urlset/manifest.mpd"
                }
            ]
        },
        "vod_h264_hls_abr": {
            "codec": "h264",
            "streaming_technique": "hls_abr",
            "has_audio_only": false,
            "max_resolution": "1080p",
            "stream": [
                {
                    "quality": null,
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/hls/dch/23506-1/h264_,LOW_THREE,LOW_TWO,LOW_ONE,MEDIUM_TWO,MEDIUM_ONE,HIGH,VERY_HIGH_ONE,.mp4.urlset/master.m3u8"
                }
            ]
        },
        "vod_h264_hls_abr_mobile": {
            "codec": "h264",
            "streaming_technique": "hls_abr",
            "has_audio_only": false,
            "max_resolution": null,
            "stream": [
                {
                    "quality": null,
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/hls/dch/23506-1/h264_,AUDIO_64,AUDIO_128,AUDIO_256,LOW_THREE,LOW_TWO,LOW_ONE,MEDIUM_TWO,MEDIUM_ONE,HIGH,VERY_HIGH_ONE,.mp4.urlset/master.m3u8"
                }
            ]
        },
        "vod_hevc_pd": {
            "codec": "hevc",
            "streaming_technique": "progressive_download",
            "has_audio_only": false,
            "max_resolution": null,
            "stream": [
                {
                    "quality": "LOW_ONE",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/hevc_LOW_ONE.mp4"
                },
                {
                    "quality": "MEDIUM_ONE",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/hevc_MEDIUM_ONE.mp4"
                },
                {
                    "quality": "HIGH",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/hevc_HIGH.mp4"
                },
                {
                    "quality": "VERY_HIGH_ONE",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/hevc_VERY_HIGH_ONE.mp4"
                }
            ]
        },
        "vod_h264_pd": {
            "codec": "h264",
            "streaming_technique": "progressive_download",
            "has_audio_only": false,
            "max_resolution": null,
            "stream": [
                {
                    "quality": "LOW_THREE",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/h264_LOW_THREE.mp4"
                },
                {
                    "quality": "LOW_TWO",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/h264_LOW_TWO.mp4"
                },
                {
                    "quality": "LOW_ONE",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/h264_LOW_ONE.mp4"
                },
                {
                    "quality": "MEDIUM_TWO",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/h264_MEDIUM_TWO.mp4"
                },
                {
                    "quality": "MEDIUM_ONE",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/h264_MEDIUM_ONE.mp4"
                },
                {
                    "quality": "HIGH",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/h264_HIGH.mp4"
                },
                {
                    "quality": "VERY_HIGH_ONE",
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dl/dch/23506-1/h264_VERY_HIGH_ONE.mp4"
                }
            ]
        },
        "vod_h264_hls_abr_max_720": {
            "codec": "h264",
            "streaming_technique": "hls_abr",
            "has_audio_only": false,
            "max_resolution": "720p",
            "stream": [
                {
                    "quality": null,
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/hls/dch/23506-1/h264_,LOW_THREE,LOW_TWO,LOW_ONE,MEDIUM_TWO,MEDIUM_ONE,HIGH,.mp4.urlset/master.m3u8"
                }
            ]
        },
        "vod_hevc_dash_abr_max_1080": {
            "codec": "hevc",
            "streaming_technique": "dash_abr",
            "has_audio_only": false,
            "max_resolution": "1080p",
            "stream": [
                {
                    "quality": null,
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/dash/dch/23506-1/hevc_,LOW_ONE,MEDIUM_ONE,HIGH,VERY_HIGH_ONE,.mp4.urlset/manifest.mpd"
                }
            ]
        },
        "vod_h264_hls_abr_secureurltest": {
            "codec": "h264",
            "streaming_technique": "hls_abr",
            "has_audio_only": false,
            "max_resolution": "1080p",
            "stream": [
                {
                    "quality": null,
                    "audio_language": null,
                    "video_language": null,
                    "url": "http://vod-world.dchdns.net/shls/dch/23506-1/h264_,LOW_THREE,LOW_TWO,LOW_ONE,MEDIUM_TWO,MEDIUM_ONE,HIGH,VERY_HIGH_ONE,.mp4.urlset/master.m3u8?token=exp=1508246208~acl=/hls/dch/23506-1/*~hmac=7f200f1b84eb4a99fc8fe12a0288500d84274fc29844b026bd093bcee344135a"
                }
            ]
        }
    }
}
```
