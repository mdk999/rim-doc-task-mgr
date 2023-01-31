[Home](../../readme.md) > [API](api.md) > Logout

### User Logout 

----

#### Sample API Request and Response
Auth: Bearer Token

Method:
- GET

Endpoint: `/v1/logout`
```json
{}
```
On Success:
```json
{
    "status": 200,
    "access_token": "[access token string]",
    "expires_in": "0",
    "description": "OK"
}
```
On Error:
```json
{
    "status": 401,
    "description": "[reason for error]"
}
```

