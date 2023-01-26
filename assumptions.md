[Home](readme.md) > Assumptions

### Assumptions (Things we're going to wish to be true)

---

- The system will allow Users to register
- The system will allow Users to login
- The system will allow Users to logout
- Tasks can only be created for the current version of the Document only
- A Task can be assigned to a single User
- A Task can be assigned to a multiple Documents
- Entities will only be 'soft' deleted from the database
- We will institute Full text search for file names
- A User can have many Documents
- A User can have many Tasks
- A Document can have many versions
- A Task will have a start and due date (can be null), and end date. The end date/completed date is when the Task is marked as completed
- A Document can have multiple active Tasks
- We will need to allow for integrating with Client's own Document Management System (DMS)


#### Tech Stack
- Front End - Nuxt/Vue.js (possibly)
- Back End - PHP/Laravel (possibly)
- Database - MySQL (possibly)
- Caching - Redis (possibly)
- Authentication - oAuth 2.0 (possibly)
- File Storage - Cloud (?)
- CLOUD (AWS, Kubernetes)
- CI/CD (Github actions / ArgoCD)
- End to End HTTPS/TLS Encryption
