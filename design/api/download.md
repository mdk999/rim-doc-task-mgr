[Home](../../readme.md) > [API](api.md) > Download

### Document Upload

----


### Sample API Request and Response (WEB)
Auth: Bearer Token

Content:
- application/json

Method:
- GET

Endpoint: `/v1/documents/{id}/url`

On Success:
```json
{
    "status": 200,
    "id": 1,
    "url": "https://url/download/document.ext",
    "expires_in": 86400,
    "description": "OK"
}
```

On Error:
```json
{
    "status": 422,
    "description": "[reason for error]"
}
```

### Sample API Request and Response (WEB)
Auth: Bearer Token

Content:
- application/stream || binary

Type: file

Method:
- GET

Endpoint: `/v1/document/{id}/download`

On Success: File is sent to the client

On Error:
```json
{
    "status": 422,
    "description": "[reason for error]"
}
```

---
### Sample API Request and Response (API)
Auth: Bearer Token

Method:
- POST

Endpoint: `/v1/user-request`
```json
{
    "user_id": "1",
    "request_type": "download",
    "url": "https://example.com",
    "method": "POST",
    "id": "1"
}
```
On Success: File is sent to the url 
On Error:
```json
{
    "status": 422,
    "description": "[reason for error]"
}
```
