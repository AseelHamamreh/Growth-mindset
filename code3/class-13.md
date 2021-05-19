# Class-13 reading Summary

### CRUD

#### HTTP Status Codes
A status code is a number higher than 100 and smaller than 600 that is part of a HTTP response. The first digit defines the class of the status. A status code comes with a reason phrase. The code is for programmatic recognition the phrase is for humans to understand what happened.

Every status code has to follow these two rules, even custom ones (yes the status codes are extensible).

#### CRUD (Create, Read, Update, Delete)
The CRUD model defines the most basic API actions for persistent storage. Create, read, update, and delete. They make up the lions-share of API endpoints. Let’s see which status codes meet their requirements.

##### CREATE
The create action is usually implemented via HTTPs POST method. In RESTful APIs, these endpoints are used to create new resources or access tokens.

##### READ
The read action gets implemented via HTTPs GET method and used to fetch resource representations. Asynchronous responses aren’t much of a thing here, because the reason for asynchronous processing is often that the resource doesn’t exist yet and has to be created, so it’s a create action anyway.

##### UPDATE
An update can be implemented with an HTTP PUT or PATCH method. The difference lies in the amount of data the client has to send to the backend.

PUT requires the client to send an entire representation of a resource to update it. (Replace the old one with the new one)

PATCH requires the client only send parts of the representation of the resource to update it. (Add, update or delete these parts in the old version)

##### DELETE
The delete action can be implemented with the HTTP DELETE method.


