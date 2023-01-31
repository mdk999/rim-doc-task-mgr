[Home](../readme.md) > [Design](design.md) > Downloads

### Document Downloads

---

#### Downloads Diagram

![Download Diagram](./images/downloads_diagram.png)

##### Web/Mobile User
- User interact with our API server(s) to get authenticated
- API server(s) responds back to User with authentication information
- User is redirected to a page/screen to get a list of Documents
- User selects a Document to download
- User chooses a 'download file' button
- Request is directed to an API server (worker node)
- Document is sent to the User with content header to initiate download

##### API User (download url request)
- User interact with our API server(s) to get authenticated
- API server(s) responds back to User with authentication information
- User is redirected to a page/screen to get a list of Documents
- User selects a Document to download
- User chooses a 'get link' button
- Request is directed to an API server (API node)
- Document url and expiration is sent to the User

##### API User (direct download)
- User sends an authenticated request to the API server for the document. 
- The API server (worker node) responds with the file (glob/binary)

##### API User (download url request)
- User sends an authenticated request to the API server for the Document url
- The API server (API node) responds with a pre-signed url for the Document with expiration

##### API User (callback download)
- User sends an authenticated request to the API server with the Document ID and callback url
- The API server (worker node) responds with the file data to the callback url
