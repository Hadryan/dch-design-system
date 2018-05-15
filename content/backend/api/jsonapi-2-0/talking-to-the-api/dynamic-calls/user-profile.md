---
title: User information
weight: 2
---

## ![](/images/shared/lock.png)

Returns the complete user profile. Request must be GET method.

Endpoint:
> /user

HTTP request header:
> Authorization: Bearer [ACCESS_TOKEN]

Response success example:
```
{
  "updated": 1478867593,
  "uid": 651983,
  "username": "j.beardi@berliner-philharmoniker.de",
  "email": "j.beardi@berliner-philharmoniker.de",
  "is_verified": true,
  "profile": {
    "firstname": "Jan",
    "lastname": "Beardi",
    "street": "Leipziger Platz 1",
    "zip": "10117",
    "city": "Berlin",
    "country": "DE",
    "permissions": {
      "can_test_livestream": true
    }
  },
  "access": {
    "type": "ticket",
    "valid": true,
    "active": true,
    "until": 1507809855
  },
  "institutional_access": {
    "status": 20,
    "is_active": false,
    "last_validated": 1477496197,
    "is_validation_needed": false,
    "institution": {
      "name": "Berlin Phil Media University",
      "street": "Leipziger Platz 1",
      "zip": "10117",
      "city": "Berlin",
      "subdivision": null,
      "country": "DE",
      "image": "images/core/iij.jpg",
      "access_begin": 1443650400,
      "access_end": 1469916000
    }
  }
}
```
TODO:
- structure of `access` and `institutional_access`. See: https://berlinphil.codebasehq.com/projects/dch-api-2/tickets/2

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
