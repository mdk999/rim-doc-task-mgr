[Home](../readme.md) > [Design](design.md) > Uploads

### Document Uploads

---

#### Uploads Diagram

![Upload Diagram](./images/uploads_diagram.png)

##### Web/Mobile User
- User interact with our API server(s) to get authenticated
- API server(s) responds back to User with authentication information
- User is redirected to a page/screen to upload Documents
- User selects a Document to upload
- Request is directed to an API server (worker node)
- Document is stored and details returned to the User

##### API User (direct upload)
- User sends an authenticated request to the API server to store the Document.
- The API server (worker node) stores the Document and details returned to the User

##### API User (callback upload)
- User sends an authenticated request to the API server with the Document details and url location
- The API server responds with the Document details and queues the request
- An API server (worker node) reads the queue and retrieves and stores the Document
- A notification is sent to the user once the Document has been uploaded
