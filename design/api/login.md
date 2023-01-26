[Home](../../readme.md) > [API](api.md) > Login

### User Login 

----

#### Sample API Request and Response
Auth: Bearer Token

Method:
- POST

Endpoint: `/v1/login`
```json
{
    "email": "me@example.com",
    "password": "L3tM31nPl3@53!"
}
```
On Success:
```json
{
    "status": 200,
    "access_token": "[access token string]",
    "expires_in": "86400",
    "id_token": "[id token string]",
    "refresh_token": "[refresh token string]",
    "token_type": "Bearer",
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

