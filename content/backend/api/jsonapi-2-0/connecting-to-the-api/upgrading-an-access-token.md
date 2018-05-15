---
title: Upgrading an access token
weight: 5
---

![](/images/shared/lock.png)

When an app already has an access token from the API 1.x and migrates to using API 2.x, it should exchange its existing token with a JWT issued by the API 2.x.

Endpoint:
> /oauth2/token

HTTP request header:
> Content-Type : application/x-www-form-urlencoded<br />

Request POST params:
- `grant_type`=exchange_token
- `app_id`=[APP_ID]
- `app_version`=[APP_VERSION]
- `client_secret`=[APP_SECRET]
- `token`=[V1_TOKEN]

*Note: Since APIv1 did not verify a clients identity, `app_id`, `app_version` and `client_secret` are mandatory here*

Response success example:
```
{
  "token_type": "Bearer",
  "expires_in": 94608000,
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6Ijk3MTIyMzQyMTM1ZGI1YjA3MDE4MDYzNzhhYTQ3MjRkYjE0ZTVmYzBkODNhODJkZDQ3ZDYyMTU0NDQ5NGVkM2M1MzgyN2IwOWRhZDM2NjExIn0.eyJhdWQiOiJkY2gucm9rdSIsImp0aSI6Ijk3MTIyMzQyMTM1ZGI1YjA3MDE4MDYzNzhhYTQ3MjRkYjE0ZTVmYzBkODNhODJkZDQ3ZDYyMTU0NDQ5NGVkM2M1MzgyN2IwOWRhZDM2NjExIiwiaWF0IjoxNDc4ODY2OTU1LCJuYmYiOjE0Nzg4NjY5NTUsImV4cCI6MTU3MzQ3NDk1NSwic3ViIjoiNjUxOTgzIiwic2NvcGVzIjpbXX0.bbAVvJzMUABUWLoHSoyvKGopJ644_5MZOICSdP_LciSaFSJQ69pQWuonl84CimPpVixqVJjWJsb9jvlfHv-UIME-BOYh0VLmNOMnqMYo6C0liMdToUpE5vCDSsrYurm064R83Zl_rw5IbvX_jSHWCF8Cp0UioPPnVG3v3O9FAHM",
  "refresh_token": "eHuWG4Kgs30QaDAFcWFYxZz/wdc7V/6NhE0RergqZ46fwIj3OI0pAAdoTMhUrfQLfl6+Ak7dvKp0APgRhQLt8x5c02q+IDqf7bPSKMyGJr+8u8thJDvqUcEEn/VKJlP39b9kgy3t6SaWhBnFJ1GivfZLbdsjdSWwIGI1t0FicqWsg59zwz80/LNozoFTPvDbJmaovBF8g2nSpa/h3ogwKrVSE0NUysqZyUv/ly1GyI8sTYDdwPMP/sxZs+c5Ydnr4fGSuXIo8XE8L5dmWDWBRuM11mixD+ovfOjWm6RYYTS/u/j4/EYkwqmKgbUKSQT+aYc92QCSVI+cf4Al+659ZnM7UOF3dFfAOyp4cwdjhGKYnpEttZcZNkjQ/Fn9/smaTdlpBtTWt6rg2IS6JtK2QSp32SDgJDfMdbMjmL2u4BiGSrx5aHCRkjWiXX0B6IKQXRiq+T0W4JxAIaWH5VjB4zDU/+FUtPOrEsjRlWl15dC4OiUcnL9xmx+s1hwoKxgs"
}
```

Error response when the given token is unknown or no token is given at all:
```
{
  "error": "invalid_request",
  "message": "Invalid or missing APIv1 token",
  "hint": "Check the \"token\" parameter"
}
```

Error response when the given token already is a JWT issued by the API 2.x:
```
{
  "error": "invalid_request",
  "message": "Token already is a JWT",
  "hint": "Check the \"token\" parameter"
}
```
