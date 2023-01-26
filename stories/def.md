## Story 1

### Ability to upload files

#### Description
In order to handle uploads an API endpoint will need to be created.

#### Value
Adding the new api end points will result in keeping personal files away from public files.

#### Acceptance Criteria
The following items must be passed via POST to `/v1/files/upload`
```json
{
    "file": "file",
    "user_id": "21d796b7-f180-499c-8783-ea2221b29810"
}
```
On Success the following message should be returned:
```json
{
    "status": 201,
    "message": "File has successfully uploaded.",
    "data": {
        "file_path": "S3 bucket url/path/to/file",
        "file_name": "myFile.docx",
        "file_url": "https://full-s3-url/to/myFile.docx"
    }
}
```
On Error the following message should be returned:
```json
{
    "status": 422,
    "message": "There was a problem uploading your file.",
}
```

#### Notes


[Back](stories.md)
