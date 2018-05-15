---
title: Updating device information
weight: 1
---

## ![](/images/shared/lock.png)

Used for keeping the device information up-to-date. For device parameters see “2.5.1 Device Detection - Parameters for Establishing a Session”. In this case all parameters are optional.

TODO: Refactor response structure. See: https://berlinphil.codebasehq.com/projects/dch-api-2/tickets/7

Endpoint:
> /device

HTTP request header:
> Content-Type : application/x-www-form-urlencoded<br />
> Authorization: Bearer [ACCESS_TOKEN]

Request POST params:
- app_id=[APP_ID]
- device_vendor=[DEVICE_VENDOR]
- affiliate=[AFFILIATE]
- app_version=[APP_VERSION]
- device_model=[DEVICE_MODEL]
- app_distributor=[APP_DISTRIBUTOR]

Response success example:
```
{
  "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6IjQ2NmFmMmFiMzc3YjI0NzM2NDdlNzkyNzU1MmVjOGQ4MjI2YTY4YzgwNmI2NjhhNjMzNjA2ZjY4YjFlMzRhMjAwNDQ1MzIzNTU2OGMxNzM4In0.eyJhdWQiOiJkY2gucm9rdSIsImp0aSI6IjQ2NmFmMmFiMzc3YjI0NzM2NDdlNzkyNzU1MmVjOGQ4MjI2YTY4YzgwNmI2NjhhNjMzNjA2ZjY4YjFlMzRhMjAwNDQ1MzIzNTU2OGMxNzM4IiwiaWF0IjoxNDc4MTc0ODYwLCJuYmYiOjE0NzgxNzQ4NjAsImV4cCI6MTQ3ODE3ODQ2MCwic3ViIjoiIiwic2NvcGVzIjpbXX0.J8yvSUB6PdLZKh3laC3V_5q4lhcMKGSe6Q5WGryEqV5-Rep59J-Xr5LjjTdAlWGaJPx9FHKauA52ynNfK_ozMYDQ-fOYp2bOruADJvva85ZRaCwKOrwHfV_g___RpuA4KK-TyoPQVn1t7cGJnhaMSJsYXvI7M9qDmQHygKpKKZU",
  "token_id": "466af2ab377b2473647e7927552ec8d8226a68c806b668a633606f68b1e34a2004453235568c1738",
  "pin": "1414002",
  "device_vendor": "roku",
  "device_model": "",
  "app_id": "dch.roku",
  "app_version": "2.1",
  "app_distributor": null,
  "affiliate": "roku"
}
```

Response example with invalid access token:
```
?
```
