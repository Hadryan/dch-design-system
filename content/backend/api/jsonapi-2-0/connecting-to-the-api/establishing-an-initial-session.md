---
title: Establishing an Initial Session
weight: 2
---
If the client has no access token or an invalid one, it has to establish an initial session to retrieve one. The initial retrieved access token will always be an anonymous one until it has been authenticated via either a password grant, a connect process on the website following a pin grant, or a registration process using the API (currently only 1.2). The access token must be stored on the device.

The lifetime of an anonymous access token is currently set to six months. After that period it will become invalid.

If the client has a stored access token, this call MUST NOT be made. Unless the replacing call for updating the device information responds that the stored access token is invalid. In this case, the client has to discard the invalid access token and establish an initial session again.

For device parameters see “[2.5.1 Device Detection - Parameters for Establishing a Session](2.0 Application/2_5_1_device_detection.md)”. Same rules for mandatory and optional parameters apply here as well.

Endpoint:
> /oauth2/token

HTTP request header:
> Content-Type : application/x-www-form-urlencoded

Request POST params:
- grant_type=device
- client_secret=[APP_SECRET]
- app_id=[APP_ID]
- device_vendor=[DEVICE_VENDOR]
- affiliate=[AFFILIATE]
- app_version=[APP_VERSION]
- device_model=[DEVICE_MODEL]
- app_distributor=[APP_DISTRIBUTOR]

Response success example:
```
{
  "token_type": "Bearer",
  "expires_in": 3600,
  "pin": "1414002",
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImp0aSI6Ijk3MTIyMzQyMTM1ZGI1YjA3MDE4MDYzNzhhYTQ3MjRkYjE0ZTVmYzBkODNhODJkZDQ3ZDYyMTU0NDQ5NGVkM2M1MzgyN2IwOWRhZDM2NjExIn0.eyJhdWQiOiJkY2gucm9rdSIsImp0aSI6Ijk3MTIyMzQyMTM1ZGI1YjA3MDE4MDYzNzhhYTQ3MjRkYjE0ZTVmYzBkODNhODJkZDQ3ZDYyMTU0NDQ5NGVkM2M1MzgyN2IwOWRhZDM2NjExIiwiaWF0IjoxNDc4ODY2NzgwLCJuYmYiOjE0Nzg4NjY3ODAsImV4cCI6MTQ3ODg3MDM4MCwic3ViIjoiIiwic2NvcGVzIjpbXX0.ZMawwksG-wODH_nwpqPO4iJ7YEQu8aa8mncTMMFujmEQFVtiIdbB5rce_EM2IFoz0YNrrPBtXudK8YqVm205hqtIX-7nx2GQJxFNq36c7oz-RpqrrVkIK1Svvsl_Yxfq-g7U27opQmhc3gvgEt72kJ0RVicvS3iQT0GW--r8JRI"
}
```

Response example with not supported APP_ID:
```
{
  "error": "invalid_client",
  "message": "Client authentication failed"
}
```

Response example with missing mandatory parameter:
```
{
  "error": "invalid_request",
  "message": "The request is missing a required parameter, includes an invalid parameter value, includes a parameter more than once, or is otherwise malformed.",
  "hint": "Check the `app_version` parameter"
}
```