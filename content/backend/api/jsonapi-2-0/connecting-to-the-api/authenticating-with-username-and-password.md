---
title: Authenticating with username and password
weight: 3
---

![](/images/shared/lock.png)
Provides a user login. The sent access token is the anonymous one the client retrieved when establishing the initial session. The received access token in this response MUST be stored on the device as this is the access token that is connected to the user.

Note: Anonymous access tokens MAY being recycled so that the one that is connected to a user will be the same as the former anonymous one. However, clients MUST store and use the newly retrieved access token in the response in order to use the right one for the time we may want no to recycle anonymous access tokens.

Endpoint:
> /oauth2/token

HTTP request header:
> Content-Type : application/x-www-form-urlencoded<br />
> Authorization: Bearer [ACCESS_TOKEN]

Request POST params:
- grant_type=password
- username=USER_EMAIL
- password=USER_PASSWORD

Response success example:
```
{
  "token_type": "Bearer",
  "expires_in": 94608000,
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6Ijk3MTIyMzQyMTM1ZGI1YjA3MDE4MDYzNzhhYTQ3MjRkYjE0ZTVmYzBkODNhODJkZDQ3ZDYyMTU0NDQ5NGVkM2M1MzgyN2IwOWRhZDM2NjExIn0.eyJhdWQiOiJkY2gucm9rdSIsImp0aSI6Ijk3MTIyMzQyMTM1ZGI1YjA3MDE4MDYzNzhhYTQ3MjRkYjE0ZTVmYzBkODNhODJkZDQ3ZDYyMTU0NDQ5NGVkM2M1MzgyN2IwOWRhZDM2NjExIiwiaWF0IjoxNDc4ODY2OTU1LCJuYmYiOjE0Nzg4NjY5NTUsImV4cCI6MTU3MzQ3NDk1NSwic3ViIjoiNjUxOTgzIiwic2NvcGVzIjpbXX0.bbAVvJzMUABUWLoHSoyvKGopJ644_5MZOICSdP_LciSaFSJQ69pQWuonl84CimPpVixqVJjWJsb9jvlfHv-UIME-BOYh0VLmNOMnqMYo6C0liMdToUpE5vCDSsrYurm064R83Zl_rw5IbvX_jSHWCF8Cp0UioPPnVG3v3O9FAHM",
  "refresh_token": "eHuWG4Kgs30QaDAFcWFYxZz/wdc7V/6NhE0RergqZ46fwIj3OI0pAAdoTMhUrfQLfl6+Ak7dvKp0APgRhQLt8x5c02q+IDqf7bPSKMyGJr+8u8thJDvqUcEEn/VKJlP39b9kgy3t6SaWhBnFJ1GivfZLbdsjdSWwIGI1t0FicqWsg59zwz80/LNozoFTPvDbJmaovBF8g2nSpa/h3ogwKrVSE0NUysqZyUv/ly1GyI8sTYDdwPMP/sxZs+c5Ydnr4fGSuXIo8XE8L5dmWDWBRuM11mixD+ovfOjWm6RYYTS/u/j4/EYkwqmKgbUKSQT+aYc92QCSVI+cf4Al+659ZnM7UOF3dFfAOyp4cwdjhGKYnpEttZcZNkjQ/Fn9/smaTdlpBtTWt6rg2IS6JtK2QSp32SDgJDfMdbMjmL2u4BiGSrx5aHCRkjWiXX0B6IKQXRiq+T0W4JxAIaWH5VjB4zDU/+FUtPOrEsjRlWl15dC4OiUcnL9xmx+s1hwoKxgs"
}
```

Response example with wrong username or password:
```
{
  "message": "Bad credentials."
}
```
TODO: add proper `error` entity. See: https://berlinphil.codebasehq.com/projects/dch-api-2/tickets/10

Response example with invalid access token:
```
{
  "error": 0,
  "message": "Invalid or missing access token"
}
```
TODO: value of `error` entity should be consistent either integer OR string. See: https://berlinphil.codebasehq.com/projects/dch-api-2/tickets/10