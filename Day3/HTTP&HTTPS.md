# HTTP & HTTPS

## 1. HTTP

**HTTP (HyperText Transfer Protocol)** is an application-layer protocol that defines how clients and servers communicate using requests and responses.

```text
Client → HTTP Request → Server
Client ← HTTP Response ← Server
```

HTTP defines the structure and meaning of communication such as methods, headers, status codes, and bodies.

---

## 2. Client

A **client** is a system that sends a request to a server.

Examples:

* Browser
* Mobile application
* Frontend application
* Postman
* Another backend service

---

## 3. Server

A **server** receives requests, processes them, and sends responses.

```text
Client → Request → Server
Client ← Response ← Server
```

---

## 4. HTTP Request

An HTTP request is sent by the client to ask the server to perform an operation.

A request can contain:

```text
HTTP Request
├── Method
├── URL / Path
├── Headers
└── Body
```

Example:

```http
POST /users HTTP/1.1
Content-Type: application/json

{
    "name": "Dhanu",
    "age": 20
}
```

---

## 5. HTTP Method

The method tells the server what operation the client wants.

Common methods:

| Method | Purpose                         |
| ------ | ------------------------------- |
| GET    | Retrieve data                   |
| POST   | Create a resource / submit data |
| PUT    | Replace a resource              |
| PATCH  | Partially modify a resource     |
| DELETE | Delete a resource               |

Easy memory:

```text
GET    → Give me
POST   → Create this
PUT    → Replace this
PATCH  → Change part of this
DELETE → Remove this
```

---

## 6. URL / Path

The path identifies the resource being requested.

Example:

```http
GET /users/10
```

```text
/users/10
    ↓
User with ID 10
```

A URL can contain:

```text
https://example.com/users/10
│       │           │
│       │           └── Path
│       └────────────── Domain
└────────────────────── Scheme
```

---

## 7. HTTP Headers

Headers provide additional information (metadata) about the request or response.

Common headers:

```text
Content-Type
Authorization
Accept
Cookie
Host
User-Agent
Cache-Control
```

Example:

```http
Content-Type: application/json
```

means the data is JSON.

---

## 8. HTTP Body

The body contains the actual data being transferred.

Example:

```json
{
    "name": "Dhanu",
    "email": "dhanu@gmail.com"
}
```

A body is optional and depends on the request or response.

---

## 9. HTTP Response

An HTTP response is sent by the server after processing a request.

A response can contain:

```text
HTTP Response
├── Status Code
├── Headers
└── Body
```

Example:

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "id": 10,
    "name": "Dhanu"
}
```

---

## 10. HTTP Status Codes

Status codes tell the client what happened to the request.

```text
1xx → Informational
2xx → Success
3xx → Redirection
4xx → Client Error
5xx → Server Error
```

Important status codes:

```text
200 → OK / Request successful
201 → Created
204 → Successful, no response body
400 → Bad Request
401 → Authentication required/failed
403 → Forbidden / Not allowed
404 → Resource not found
500 → Internal Server Error
```

### 401 vs 403

```text
401 → "Who are you?"
403 → "I know who you are, but you're not allowed."
```

---

## 11. HTTP is Stateless

HTTP is generally **stateless**, meaning each request is independent.

HTTP itself does not automatically remember previous requests.

Applications use mechanisms such as:

* Cookies
* Sessions
* Tokens
* JWT

to maintain user identity or state.

---

# HTTPS

## 12. HTTPS

**HTTPS (HyperText Transfer Protocol Secure)** is HTTP communication protected using **TLS (Transport Layer Security)**.

```text
HTTPS = HTTP + TLS
```

HTTPS provides:

* Confidentiality through encryption
* Integrity protection
* Server authentication

---

## 13. TLS

**TLS (Transport Layer Security)** is a security protocol used to protect communication over a network.

TLS provides:

```text
TLS
├── Encryption / Confidentiality
├── Integrity
└── Authentication
```

---

## 14. Encryption

Encryption converts readable data into protected ciphertext so that unauthorized parties cannot simply read it.

```text
Readable Data
     ↓
Encryption
     ↓
Protected Data
```

HTTPS uses TLS to protect HTTP communication.

---

## 15. Integrity

Integrity helps ensure that data has not been secretly modified while travelling between the client and server.

Example:

```text
Client → "Transfer ₹1000"
```

An attacker should not be able to silently change it to:

```text
"Transfer ₹100000"
```

without the modification being detected.

---

## 16. Authentication

HTTPS uses TLS certificates to help the client verify the identity of the server it is connecting to.

A certificate is part of the mechanism used to authenticate the server and establish secure communication.

---

## 17. SSL Certificate

The term **SSL certificate** is commonly used, but modern HTTPS uses **TLS** rather than the old SSL protocol.

A certificate contains information about the domain/server identity and a public key and is used during the TLS connection.

---

## 18. HTTP vs HTTPS

| HTTP              | HTTPS                                   |
| ----------------- | --------------------------------------- |
| HTTP protocol     | HTTP protected by TLS                   |
| No TLS protection | Encryption + integrity + authentication |
| Usually port 80   | Usually port 443                        |
| Less secure       | Secure communication                    |

---

# Complete Website Flow

When opening:

```text
https://example.com
```

a simplified flow is:

```text
1. DNS
   ↓
   Find the server IP

2. TCP
   ↓
   Establish reliable communication

3. TLS
   ↓
   Establish secure communication

4. HTTP
   ↓
   Send the HTTP request

5. Server
   ↓
   Process request

6. HTTP Response
   ↓
   Send status + headers + data

7. Browser
   ↓
   Process and display the response
```

### Key sentence

> **DNS finds the server, TCP provides reliable transport, TLS secures the connection, and HTTP defines the request and response.**

---

# HTTP Request-Response Example

Request:

```http
POST /users HTTP/1.1
Content-Type: application/json

{
    "name": "Dhanu",
    "age": 20
}
```

Server processes it:

```text
Controller
    ↓
Service
    ↓
Repository
    ↓
Database
```

Response:

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
    "id": 101,
    "name": "Dhanu",
    "age": 20
}
```

---

