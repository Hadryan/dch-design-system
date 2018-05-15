---
title: User favourites
weight: 3
---

## ![](/images/shared/lock.png)

Return/update the user’s favourites. 

###### Retrieving the favourites

- Endpoint: `/user/favourites`
- Request method: `GET`

HTTP request header:
`Authorization: Bearer [ACCESS_TOKEN]`

###### Updating the favourites

- Endpoint: `/user/favourites`
- Request method: `POST`
- Request parameters:
  - `action=(add|delete)`
  - `id=[ID]`
- HTTP request headers:
```
Authorization: Bearer [ACCESS_TOKEN]
Content-Type : application/x-www-form-urlencoded
```

Response success example:
```
{
  "updated": 1475074300,
  "_links": {
    "favourites": [
      {
        "href": "//tv-dev1.dchdev.net/v2/work/23427-1",
        "updated": 1475074300,
        "id": "23427-1",
        "title": "[Éclat] (1st Version for 15 instruments from 1965)",
        "short_title": null,
        "is_free": false,
        "date": {
          "published": 1472720400,
          "begin": 1472229000
        },
        "image": {
          "overview": "//www-dev1.dchdev.net/cms/thumbnails/{width}x{height}/images/core/BPhil_SSR_260816_040_DCH.jpg",
          "detail": "//www-dev1.dchdev.net/cms/thumbnails/{width}x{height}/images/core/BPhil_SSR_260816_040_DCH.jpg"
        },
        "type": "work"
      },
      {
        "href": "//tv-dev1.dchdev.net/v2/interview/23427-3",
        "updated": 1473077071,
        "id": "23427-3",
        "title": "Introduction by Sir Simon Rattle",
        "short_title": null,
        "is_free": true,
        "date": {
          "published": 1472720400,
          "begin": 1472229000
        },
        "image": {
          "overview": null,
          "detail": null
        },
        "type": "interview"
      },
      {
        "href": "//tv-dev1.dchdev.net/v2/film/301",
        "updated": 1464622718,
        "id": "301",
        "title": "“Guardians of Unity”: Conductors in conversation",
        "is_free": false,
        "date": {
          "published": 1463558400
        },
        "image": {
          "overview": "//www-dev1.dchdev.net/cms/thumbnails/{width}x{height}/images/core/Hueter_Kreis_schwarz_en.jpg",
          "detail": "//www-dev1.dchdev.net/cms/thumbnails/{width}x{height}/images/core/dirigentenfilm_dch.jpg"
        },
        "type": "film"
      }
    ]
  }
}
```

Response example with invalid access token:
```
{
  "message": "A Token was not found in the TokenStorage."
}
```

Response example with POST instead of GET method:
```
{
  "error": {
    "message": "No route found for \"POST /v2/user\": Method Not Allowed (Allow: GET)"
  }
}
```