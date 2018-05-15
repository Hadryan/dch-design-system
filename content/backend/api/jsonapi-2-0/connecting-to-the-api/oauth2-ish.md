---
title: OAuth2(-ish)
weight: 1
---

##### Access tokens

OAuth secured calls require a set authorization header with an API 2.0 access token. These calls are marked with ![](/images/shared/lock.png) in the documentation.

An access token can be one for an anonymous user or one for a logged in user. These tokens come in the form of a JWT (see https://jwt.io/).

The concept of expiring access tokens and retrieving new access tokens with a refresh token is not fully implemented yet and won't be available for some time after the initial launch of API 2.0. Therefore, access tokens have a life time of 3 years at the moment and clients will not have to store refresh tokens or try to retrieve a new access token if the current access token is invalid. However, access tokens can also become invalid when the user deletes the connection of a specific device to his account remotely via our website. So clients MUST treat this scenario as if the user has disconnected his device.

##### Verifying the access token

All access tokens are signed by the API using a 1024-Bit RSA key. Thus, if a client chooses to do so, it can verify the token using the APIs public key (see https://jwt.io/introduction/#signature for details).
Currently the APIs public keys are as follows:

**DEV**:

```
-----BEGIN PUBLIC KEY-----
MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQC05FxcaYuCGAebxzH8SgSa9tt7
h7DFXgewczH5nLyBjfdhJTZaJCiSdpYolQF1aLYh247MqyQ2C397W/3lir/D2dZN
g/DyZKkYsxh7PJGd1egojWz2lU0EoLxSYB+rDzZrnCLTO/cqCFBD5jjsuso7gNsB
3w6WzeCWFXokLEdP3wIDAQAB
-----END PUBLIC KEY-----
```

**TEST**:

```
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAz2lk2c64Lw59Ch54AeUO
i7HYD1dRWFNYd2fJ+1R8ZHoEB5l2pK4mufeW9TS6KMnlAiubspBBUHG//OT7mQcG
r7MPjDAYYbr3pavUX6EvfzYIpnFQ68yFuRzOal9P9MKneSeSZUmrS9WQ1Gl76s6u
TMz/FIHXfvON0UAYBvYkcxfsDs0eaRdi+9uJCADsrOkkd09bL9VeSn3o8EGzmZIh
1aAr3yZBmj57cpeJjDnGueics4E0ILswAUn0EE4DhwsiSoZ9FGzdZ+g5zOmfGTwP
+g4f6ry+BcTMPr1hRehBR1Bkz5c9Ha3SlhHWGvbZBPC8IZ2q/4cuvYobWg9XS+46
QQIDAQAB
-----END PUBLIC KEY-----
```


**LIVE**:

```
-----BEGIN PUBLIC KEY-----
MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDsi8HhA9JKVGa/qH3kku0vOTJd
WsGP1MIKyreNKdwsqeVj5CURck5lQcAfYiVdSDvB6BC1lNWHU+aMPFyYUpkQtzLj
nQq15UEiL1CRpU6z0l7K9blP1iKygdYY8SFLZ3qe+FnSmj5EJBYZ+f5rYjqgj26l
IdX8k2/wQ0i/1bO9fQIDAQAB
-----END PUBLIC KEY-----

```

##### Client secrets
To establish an initial session (see below), clients MUST use an application and environment specific secret (APP_SECRET), while all subsequent secured calls will be authorized using an access token retrieved in that process. The following app secrets exist:

| App ID            | DEV        | TEST       | LIVE | Notes                             |
| ----------------- | ---------- | ---------- | ---- | --------------------------------- |
| dch.roku          | ge6veu9Vie | 16FLu8MGqu | OcwaMqtWYL |                                   |
| dch.ios           | Mah3tuLaec |            | QRGjOtHnr8 |                                   |
| dch.windows       | Aeghai4ra0 |            | omfALXbI/B |                                   |
| dch.tvos          | maV5aagh4a |            | BDClwZyeIF |                                   |
| dch.tv            | OTh8eexi7I |            | 7+M21nXBVr |                                   |
| dch.android       | Uquoopae0o |            | fWl0GiyyoU |                                   |
| dch.tv.html5      | Zuquahdah6 |            | AhjcW5CjXx |                                   |
| dch.tv.netcast    | ooNgimoo0m |            | 708vjkqdM3 |                                   |
| dch.tv.webos      | iDeeJeezi6 |            | biQG8j13Rv |                                   |
| dch.tv.orsay      | aeg1noH1di |            | XvdlwP5UR2 |                                   |
| dch.tv.tizen      | TaiSh9ohm1 |            | YDPr3BkFDk |                                   |
| dch.tv.androidtv  | miveegh2Ik |            | CEorttmqDG |                                   |
| dch.tv.firetv     | Mei9Ies1ez |            | S/O4HB1Fz6 |                                   |
| dch.test.lx       | WohrooV9Oo | 3U7gKDT9Ds | 6ncHyaP3hl | Used by Alex for testing          |
| dch.test.runscope | ye8Fu2Oo   |            | mUGv5WDaGJ | Used for Runscope tests           |

