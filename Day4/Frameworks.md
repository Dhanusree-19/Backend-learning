# Backend Frameworks

## What is a Framework?

A framework is a **pre-built structure and set of tools** that helps developers build applications faster and in an organized way.

Instead of building common backend functionality from scratch, a framework provides features for:

* Request handling
* Routing
* Database integration
* Validation
* Security
* Error handling
* Application structure

```text
Client
  ↓
Framework
  ↓
Application Logic
  ↓
Database / Services
```

# What Happens Without a Framework?

A framework is not mandatory. We can build a backend without one.

But we would have to handle many common tasks ourselves.

For example, a backend needs to handle:

```text
HTTP Request
     ↓
Start / manage server
     ↓
Read request
     ↓
Identify URL and HTTP method
     ↓
Routing
     ↓
Parse JSON
     ↓
Validate data
     ↓
Business Logic
     ↓
Database Connection
     ↓
Database Query
     ↓
Create Response
     ↓
Send HTTP Response
```

Without a framework, we would need to implement or manage much more of this infrastructure ourselves.

### Example

Suppose we want:

```text
GET /users
```

Without a framework, we may need to manually handle:

* Starting the HTTP server
* Listening for requests
* Reading the request
* Checking the URL
* Checking the HTTP method
* Routing the request
* Parsing request data
* Handling errors
* Creating the response
* Managing database connections
* Converting data to JSON

With a framework such as Spring Boot:

```text
HTTP Request
     ↓
Spring Boot
     ↓
Controller
     ↓
Service
     ↓
Repository
     ↓
Database
     ↓
Response
```

For example:

```java
@GetMapping("/users")
public List<User> getUsers() {
    return userService.getUsers();
}
```

Spring Boot handles much of the underlying web infrastructure, allowing the developer to focus mainly on the application's logic.

## Important Point

**Without a framework:** More infrastructure and common functionality must be built or configured manually.

**With a framework:** Common infrastructure is provided, so development becomes faster, more structured, and easier to maintain.

A framework does **not** eliminate backend development. It provides the foundation on which we build the backend application.


# Framework vs Language vs Runtime

These are different things.

| Technology   | What it is                           |
| ------------ | ------------------------------------ |
| Java         | Programming Language                 |
| Python       | Programming Language                 |
| JavaScript   | Programming Language                 |
| Node.js      | JavaScript Runtime                   |
| Spring Boot  | Java Backend Framework               |
| Django       | Python Web Framework                 |
| FastAPI      | Python API Framework                 |
| Express.js   | Node.js Backend Framework            |
| NestJS       | Node.js/TypeScript Backend Framework |
| ASP.NET Core | C# Backend Framework                 |
| Laravel      | PHP Web Framework                    |

Example:

```text
Java
 ↓
Spring Boot
 ↓
Backend Application
```

---

# Common Backend Frameworks

### Spring Boot — Java

Used for:

* Enterprise applications
* REST APIs
* Large backend systems
* Microservices
* Banking and business applications

```text
Java → Spring Boot → Backend
```

### Django — Python

Used for:

* Full-featured web applications
* Websites
* Backend systems

Django provides many features out of the box.

```text
Python → Django → Web Application
```

### FastAPI — Python

Used mainly for:

* APIs
* AI/ML services
* Data services
* Microservices

```text
Python → FastAPI → API
```

### Express.js — Node.js

A lightweight and flexible framework for building:

* REST APIs
* Web servers
* Backend applications

```text
JavaScript → Node.js → Express.js → Backend
```

### NestJS — TypeScript

Used for:

* Structured backend applications
* Large APIs
* Enterprise applications
* Microservices

```text
TypeScript → NestJS → Backend
```

### ASP.NET Core — C#

Used for:

* Enterprise applications
* Web APIs
* Cloud applications

```text
C# → ASP.NET Core → Backend
```

### Laravel — PHP

Used for:

* Web applications
* REST APIs
* Database-driven applications

```text
PHP → Laravel → Backend
```

---

