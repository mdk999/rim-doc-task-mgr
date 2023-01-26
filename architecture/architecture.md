[Home](../readme.md) > Architecture

### Architecture (parts of the machine)

----

#### EKS is configured as follows

- Dev Cluster
- Stage Cluster
- Prod Cluster

#### Each cluster has Nodes which contains Pods for 
- Web server - Nginx + Nuxt.js
  - Serves static assets
- API Server - PHP + Laravel
  - Handles API requests, Authentication
- Laravel Workers - PHP + Laravel
  - Handles long-running jobs and tasks
  - Uploads
  - Downloads
  - Messaging
  - Notifications
  - Queue requests


#### Upload

##### Web/Mobile User
1. User authenticates
2. From the browser or UI, client selects which file(s) they would like to upload from their local folder
3. If any constraints to file type, size, extension and error is thrown
4. File sent to the cluster when then redirects to a worker
5. Worker creates a DB entry for the file with an `upload_status` ie pending, completed or failed

##### API User
- API users have two means of uploading
1. Sending a POST request to the API endpoint [/v1/document](../design/api/upload.md)
2. Send a POST request to the API endpoint [/v1/user_requests](../design/api/upload.md). This endpoint will create 
a queued job which will fetch and store the file. 


#### Download

##### Web/Mobile User
1. User authenticates
2. From the browser or UI, client selects from a list of files from the document list dashboard
3. Client can select if they want a link or to download the file
   - If client selects a `link`, an API request is made to [/v1/document/{id}/url](../design/api/download.md). This 
   generates a Pre-signed URL for the client and returns that along with an expiration
   - If the client selects to download the file, an API request is made to  [/v1/document/{id}/download](../design/api/download.md)
   - The file is then sent to the browser with a content type which initiates the download

##### API User
- API users have two means of downloading the file
1. Sending a POST request to [/v1/document/{id}/url](../design/api/download.md)
2. Send a POST request to the API endpoint [/v1/user_requests](../design/api/download.md). This endpoint will create
   a queued job which will stream the file. 


##### Client Document Management System
We've implemented a fully customizable webhook/callback system. Clients can configure an endpoint, http method, url and
token that our system will queue requests and send files. Clients can even customize the payload by using mappings
to map our data to theirs.
