[Home](../../readme.md) > [API](api.md) > Upload

### Document Upload

----


### Sample API Request and Response (WEB)
Auth: Bearer Token

Content:
- multipart/form-data

Type: file
name: myfile.txt

Method:
- POST

Endpoint: `/v1/documents`
```json
{
    "user_id": "1"
}
```
On Success:
Header:
"Location": "/v1/documents/[newly created resource id]",
```json
{
    "status": 201,
    "id": 1,
    "name": "myfile.txt",
    "version": 1,
    "user_id": 1,
    "size": "455656",
    "mime_type": "text/plain",
    "ext": "txt",
    "created_at": "2023-01-06 17:14:27",
    "updated_at": "",
    "deleted_at": "",
    "private": 0,
    "parent_document": 1,
    "upload_status": "completed",
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

---
### Sample API Request and Response (API)
Auth: Bearer Token

Method:
- POST

Endpoint: `/v1/user-requests`
```json
{
    "user_id": "1",
    "request_type": "upload",
    "url": "https://example.com/myfile.zip",
    "method": "GET"
}
```
On Success:
```json
{
  "status": 201,
  "id": 2,
  "name": "myfile.zip",
  "version": 1,
  "user_id": 1,
  "size": "4556546",
  "mime_type": "application/zip",
  "ext": "zip",
  "created_at": "2023-01-06 18:14:27",
  "updated_at": "",
  "deleted_at": "",
  "private": 0,
  "parent_document": 2,
  "upload_status": "pending",
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
