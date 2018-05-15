---
title: Logging
weight: 6
---

## 3.5.1 Tracking Stream Minutes

If a client plays back video content (except for trailers and previews) it has to report every minute watched, regardless if it is paid or free content. This mechanism is crucial as it is used for calculating license fees. This also applies to audio only streams if an application implements this feature. In JSONAPI 1.2 this is done via the streamlog call. The logging system is separated from the core system and therefore it has to manage device information for itself. It also needs less device information.

| Parameter | Optional | Purpose |
| -- | -- | -- |
| device_vendor | no | actual manufacturer of that device |
| app_id | no | DCH internal ID of the app for that platform |
| ts | no | UNIX timestamp of the client |
| pos | no | current play position of the video/audio in seconds - for vod concerts this means the position in the currently played work, for *live concerts this must always be the negative value* `-1`. The value of pos must never be bigger than the duration of the content, this has to be validated on client side |
| dur | no | current watched duration of the video/audio in seconds |
| uid | no | user ID |
| productid | no | ID of the current work, film or live concert - films and live concerts MUST NOT report any work ID but it's own ID (without `-X`) |
| hash | no | MD5 hash of the concatenation of API_KEY + UID + TS<br />Example: `md5("APIKEY2351399966666")` when timestamp is `1399966666`, user ID is `235` and the API key is `APIKEY` |
| offline | yes | must be 1 when reporting minutes watched offline |
| audio | yes | must be 1 when reporting minutes of audio only streams |

API keys are available for every combination of a platform and DCH environment (DEV, TEST, LIVE) and must be requested at SkyGate.

The first call SHOULD be made after the first minute watched/listened. The subsequent call SHOULD be made when the current watched/listened duration hits exactly one minute more than before. Pausing a video or audio stream MUST assure that the duration will not be increased before the playback is started again. Skipping and trickplay MUST also assure that the duration will not change. They will only change the position. If a new video or audio stream is played back, the duration MUST be resetted first. This also applies if the new stream is the same as before. This could be the case when a user stops the playback (closes the player) and then decides to watch it/listen to it again.

In brief:
1. Duration changes only in play mode
2. Call will only be made after every 60 seconds added to the duration

When reporting offline watched/listened content, a client MUST send every minute as a separate call after it gained access to the internet again.

### Endpoints

| DCH Environment | URL |
| -- | -- |
| DEV | https://sl-dev.digitalconcerthall.com/streamlog.php |
| TEST | http://api-test.dchdev.net/streamlog.php |
| LIVE | https://api.digitalconcerthall.com/streamlog.php |

TODO: Is SSL really mandatory? TEST URL is not SSL in this example
Die Nutzung von SSL für die Aufrufe ist verpflichtend. Meldet der Streamlog-Server einen HTTP-Code 500 zurück, deutet dies auf fehlende oder falsche Parameter hin. Kann die Ursache nicht geklärt werden, kann SkyGate unter Angabe der genauen Uhrzeit über ein Logfiles bei Bedarf genauer sagen, woran der Aufruf scheitert.

---


## 3.5.2 Logging Errors
