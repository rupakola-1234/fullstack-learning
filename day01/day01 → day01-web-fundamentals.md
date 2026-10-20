# Day 1 — Understanding Web Applications

## Objective

Understand how a modern web application works from the browser to the backend and database.

## 1. What is a Web Application?

A web application is a software application that runs through a web browser. Users can interact with the application using a browser such as Google Chrome, Microsoft Edge, or Firefox.

Examples of web applications include Gmail, Amazon, Instagram, online banking applications, and task management applications.

A web application usually has three main parts:

- **Frontend** — The part that the user sees and interacts with.
- **Backend** — The part that processes requests and performs application logic.
- **Database** — The part that stores application data.

## 2. Frontend vs Backend

### Frontend

The frontend is the part of a web application that the user can see and interact with.

Examples include:

- Buttons
- Forms
- Menus
- Text
- Images
- Task lists

React is commonly used to build the frontend of modern web applications.

### Backend

The backend is the part of the application that works behind the scenes. It receives requests from the frontend, processes the data, applies application logic, and communicates with the database.

FastAPI is a Python framework that can be used to build the backend and APIs.

### Difference

| Frontend | Backend |
|---|---|
| Visible to the user | Works behind the scenes |
| User interface | Application logic |
| Runs mainly in the browser | Runs on a server |
| Example: React | Example: FastAPI |

## 3. Browser and Web Server

A **browser** is a software application used to access web applications. Examples include Google Chrome, Microsoft Edge, and Firefox.

A **web server** is a computer or software that receives requests from a browser and sends responses back to it.

The basic communication is:

```text
Browser
   |
   | Request
   ↓
Web Server
   |
   | Response
   ↓
Browser
```

The browser acts as the **client**, and the web server acts as the **server**.

## 4. Client-Server Architecture

Client-server architecture is a model where a **client** sends a request to a **server**, and the server processes the request and sends a response back.

In a web application:

- The **browser** is usually the client.
- The **server** processes the request.
- The client and server communicate using HTTP or HTTPS.

Basic flow:

```text
Client (Browser)
       |
       | Request
       ↓
     Server
       |
       | Response
       ↓
Client (Browser)
```

For example, when a user opens a task management application, the browser may request the list of tasks from the server. The server processes the request and sends the task data back to the browser.

## 5. What is an API?

API stands for **Application Programming Interface**.

An API allows different software applications to communicate with each other.

In a web application, the frontend can communicate with the backend through an API.

For example:

```text
React Frontend
      |
      | HTTP Request
      ↓
     API
      |
      ↓
FastAPI Backend
```

The API receives requests from the frontend and allows the backend to process those requests.

For example, a task application may have an API endpoint:

```text
GET /tasks
```

This endpoint can be used to request the list of tasks from the backend.

## 6. HTTP and HTTPS

**HTTP** stands for **HyperText Transfer Protocol**. It is a communication protocol used to transfer data between a client, such as a browser, and a server.

**HTTPS** stands for **HyperText Transfer Protocol Secure**. It is the secure version of HTTP and encrypts the communication between the browser and the server.

Example:

```text id="u4e9s0"
Browser
   |
   | HTTPS
   ↓
Server
```

HTTPS helps protect information such as passwords and other sensitive data while it is being transferred.

Therefore, HTTPS is preferred over HTTP for modern web applications.

## 7. HTTP Request and Response

An **HTTP request** is a message sent by a client, such as a browser or frontend application, to a server.

An **HTTP response** is the message sent back by the server after processing the request.

The basic flow is:

```text
Browser / React
      |
      | HTTP Request
      ↓
FastAPI Backend
      |
      | HTTP Response
      ↓
Browser / React
```

For example, when a user wants to see a list of tasks:

```text
Request:
GET /tasks

Response:
[
  {
    "id": 1,
    "title": "Learn FastAPI"
  }
]
```

The request asks the server for information, and the response contains the requested information.

## 8. URL, Endpoint, Headers and Body

### URL

URL stands for **Uniform Resource Locator**. It is the address used to locate a resource on the internet.

Example:

```text
https://example.com/tasks
```

### Endpoint

An endpoint is a specific URL or path through which an API provides a particular operation.

Example:

```text
GET /tasks
```

Here, `/tasks` is the endpoint path.

### Headers

Headers contain additional information about an HTTP request or response.

For example:

```text
Content-Type: application/json
```

This tells the server that the data being sent or received is in JSON format.

### Body

The body contains the actual data sent with an HTTP request.

For example, when creating a new task:

```json
{
  "title": "Learn FastAPI"
}
```

The task information is sent in the request body.

## 9. HTTP Methods

HTTP methods tell the server what operation the client wants to perform.

| Method | Purpose | Example |
|---|---|---|
| GET | Read or retrieve data | `GET /tasks` |
| POST | Create new data | `POST /tasks` |
| PUT | Replace or completely update data | `PUT /tasks/1` |
| PATCH | Partially update data | `PATCH /tasks/1` |
| DELETE | Delete data | `DELETE /tasks/1` |

### GET

GET is used to retrieve data from the server.

```text
GET /tasks
```

### POST

POST is used to create new data.

```text
POST /tasks
```

### PUT

PUT is used to completely replace or update existing data.

```text
PUT /tasks/1
```

### PATCH

PATCH is used to partially update existing data.

```text
PATCH /tasks/1
```

### DELETE

DELETE is used to remove data.

```text
DELETE /tasks/1
```

These methods are commonly used to perform CRUD operations in web applications.

## 9. HTTP Methods

HTTP methods tell the server what operation the client wants to perform.

| Method | Purpose | Example |
|---|---|---|
| GET | Read or retrieve data | `GET /tasks` |
| POST | Create new data | `POST /tasks` |
| PUT | Replace or completely update data | `PUT /tasks/1` |
| PATCH | Partially update data | `PATCH /tasks/1` |
| DELETE | Delete data | `DELETE /tasks/1` |

### GET

GET is used to retrieve data from the server.

```text
GET /tasks
```

### POST

POST is used to create new data.

```text
POST /tasks
```

### PUT

PUT is used to completely replace or update existing data.

```text
PUT /tasks/1
```

### PATCH

PATCH is used to partially update existing data.

```text
PATCH /tasks/1
```

### DELETE

DELETE is used to remove data.

```text
DELETE /tasks/1
```

These methods are commonly used to perform CRUD operations in web applications.

## 10. HTTP Status Codes

HTTP status codes tell the client whether a request was successful or whether there was an error.

| Status Code | Meaning | Example |
|---|---|---|
| `200` | OK — request was successful | Data was retrieved successfully |
| `201` | Created — new data was created | A new task was created |
| `400` | Bad Request | Invalid data was sent |
| `401` | Unauthorized | Authentication is required |
| `403` | Forbidden | The user is not allowed to access the resource |
| `404` | Not Found | The requested task does not exist |
| `500` | Internal Server Error | An unexpected error occurred on the server |

### Example

If a user creates a new task successfully, the server may return:

```text id="4e2l2r"
201 Created
```

If the user requests a task that does not exist, the server may return:

```text id="e4d4l4"
404 Not Found
```

Status codes help the frontend understand the result of an HTTP request.

## 11. JSON

JSON stands for **JavaScript Object Notation**.

JSON is a simple format used to store and exchange data between applications. It is commonly used when a frontend communicates with a backend through an API.

Example:

```json
{
  "id": 1,
  "title": "Learn FastAPI",
  "completed": false
}
```

In this example:

- `id` is the task ID.
- `title` contains the task name.
- `completed` tells whether the task is completed.

A React frontend can send JSON data to a FastAPI backend, and FastAPI can return JSON data in its response.

## 12. How React, FastAPI and a Database Fit Together

A modern web application can use different technologies for different parts of the application.

- **React** is used to build the frontend and user interface.
- **HTTP API** is used for communication between the frontend and backend.
- **FastAPI** is used to build the backend and API.
- **Database** is used to store application data.

The basic architecture is:

```text
┌───────────────┐
│    Browser    │
│               │
│     React     │
└───────┬───────┘
        │
        │ HTTP Request / Response
        ↓
┌───────────────┐
│   HTTP API    │
└───────┬───────┘
        │
        ↓
┌───────────────┐
│    FastAPI    │
│    Backend    │
└───────┬───────┘
        │
        │ SQL
        ↓
┌───────────────┐
│    Database   │
└───────────────┘
```

For example, when a user creates a task, React collects the task information and sends it to a FastAPI API. FastAPI processes the request and stores the task in the database. The backend then sends a response back to React, and React displays the result to the user.

## 13. What Happens When a User Submits a Form?

Consider a task management application where a user enters a task and clicks the **Add Task** button.

The following steps happen:

1. The user enters the task in a form in the browser.
2. React collects the information entered by the user.
3. React sends an HTTP `POST` request to the API.
4. The API receives the request and sends it to the FastAPI backend.
5. FastAPI validates and processes the submitted data.
6. FastAPI sends the data to the database.
7. The database stores the new task.
8. The database sends the result back to FastAPI.
9. FastAPI sends an HTTP response back to React.
10. React updates the screen and displays the newly created task.

The complete flow is:

```text
User
  ↓
Browser
  ↓
React
  ↓
HTTP POST Request
  ↓
API
  ↓
FastAPI
  ↓
Database
  ↓
FastAPI
  ↓
HTTP Response
  ↓
React
  ↓
Browser
  ↓
User sees the new task
```

For example, if the user enters:

```json
{
  "title": "Learn FastAPI"
}
```

React sends this information to the backend. FastAPI processes it and stores it in the database. After successful storage, the backend can return a response such as `201 Created`.

## 14. Difference Between Frontend, Backend, API and Database

| Part | Meaning | Main Responsibility | Example |
|---|---|---|---|
| Frontend | User-facing part of the application | Displays information and accepts user input | React |
| Backend | Server-side part of the application | Processes requests and application logic | FastAPI |
| API | Communication interface between applications | Sends and receives data between frontend and backend | HTTP API |
| Database | Data storage system | Stores and retrieves application data | PostgreSQL |

### Frontend

The frontend is what the user sees and interacts with. It contains elements such as buttons, forms, menus, and pages.

### Backend

The backend works behind the scenes. It processes requests, performs application logic, validates data, and communicates with the database.

### API

The API provides a way for the frontend and backend to communicate. It receives requests and sends responses using HTTP.

### Database

The database stores application data so that the information can be retrieved later. For example, a task manager can store task IDs, task names, and completion status in a database.nest

