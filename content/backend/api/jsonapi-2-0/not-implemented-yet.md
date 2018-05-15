---
title: Not implemented yet
weight: 3
---

Some calls are not yet implemented in the API 2.0. 
These calls must be made via API 1.2 as a workaround. Every API 1.2 call that needs an API 1.2 device token will work right out of the box with the ID of an API 2.0 access token instead.

The API 2.0 access token’s ID can be retrieved through the payload of that token (see https://jwt.io/). Note: The ID is not retrieved through the response of any API 2.0 call. It is instead encoded in the access token itself. The access token must be decoded in order to retrieve the payload and with that the access token's ID.

To do that, you have to base64 encode the middle part (`.` is the delimiter) of the API 2.0 access token. You will retrieve something like `{"aud":"dch.tv.html5","jti":"ffa83678091f33f10c42deecdd1a2508e701e5b69c9e3f242938ed5ff5391051b846d24104a22f68","iat":1501498178,"nbf":1501498178,"exp":1596192578,"sub":"912162","scopes":[]}`, where `jti` is the ID of that access token.

##### short_register
Provides a user registration.

See: https://docs.digitalconcerthall.com/3.0%20Database%20and%20API/3_3_jsonapi_1_2.html#261-kurzregistrierung-shortregister

Request:
```
{
    'cmd':        'short_register'
    'email:'      <STRING>
    'password':   <STRING>
    'firstname':  <STRING>,
    'lastname':   <STRING>,
    'salutation': <INT>,    // 1: Herr, 2: Frau
    'country':    <STRING>  // Countrycode (ISO 3166-1 alpha-2, für gültige Werte siehe "get_countries")
}
```

Response: can be ignored if not an error

##### resend_activation_mail
Request with API 2.0 access token ID.

See: https://docs.digitalconcerthall.com/3.0%20Database%20and%20API/3_3_jsonapi_1_2.html#263-erneutes-anfragen-der-registrierungs-bestätigungs-mail-resendactivationmail

Request:
```
{
    'cmd': 'resend_activation_mail'
}
```

##### disconnect
Request with API 2.0 access token ID.

Note: As long as there is no replacement call available in the JSONAPI 2, the returned device token in this call should be ignored. Instead, a client has to treat a user disconnect like a fresh start and with that, retrieve a new anonymous access token from the JSONAPI 2 via https://docs.digitalconcerthall.com/3.0%20Database%20and%20API/3_4_jsonapi_2_0.html#establishing-an-initial-session

See: https://docs.digitalconcerthall.com/3.0%20Database%20and%20API/3_3_jsonapi_1_2.html#23-logout-disconnect

Request:
```
{
    'cmd':      'disconnect',
    'token':    <STRING>
}
```

##### ping.php (Concurrent Session Blocking)
Will work with the API 2.0 access token IDs as well as with an API 1.2 access token. MUST be checked every 60 seconds while playing back video content. The playback MUST be stopped only if this call returns exactly `0`. Also bad HTTP requests MUST NOT stop the playback.

Endpoint for DEV:
> //tv-dev1.dchdev.net/miniscripts/ping.php

Endpoint for LIVE:
> //api.digitalcncerthall.com/miniscripts/ping.php

Request GET params:
- token=ACCESS_TOKEN_ID

Response success example:
```
OK
```

Response example when concurrent usage is detected:
```
0
```

##### streamlog.php (Stream Minute Logging)
As it uses the user ID, it should work right of the box.

See: https://docs.digitalconcerthall.com/3.0%20Database%20and%20API/3_5_logging.html#351-tracking-stream-minutes

## Testing
There is a availability and consistency test for API 2.0 on Runscope called "API 2.0 Availability on DEV1". The base url for the environment is http://tv-dev1.dchdev.net/v2. This test must be manually triggered with following url:

https://api.runscope.com/radar/12367a60-b5cc-4ddd-8acc-8ee23eb80d8c/trigger?runscope_environment=ec4f43bf-b145-4220-9a22-92ce625575bc

The results of each test can be accessed through the Runscope web interface and will also be pushed to our Slack channel #dch-core-api-tests.

Current assertions are:

| Call           | Assertion                         |
| -------------- | --------------------------------- |
| /manifest      | returns 200 OK                    |
| /home          | returns 200 OK                    |
| /concerts/vod  | returns 200 OK                    |
| /concerts/live | returns 200 OK                    |
| /concerts/live | no concert begin date at midnight |
| /films         | returns 200 OK                    |
| /interviews    | returns 200 OK                    |
| /categories    | returns 200 OK                    |
| /genres        | returns 200 OK                    |
| /epochs        | returns 200 OK                    |
| /seasons       | returns 200 OK                    |
| /collections   | returns 200 OK                    |

