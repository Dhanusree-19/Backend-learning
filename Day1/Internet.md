# Internet & Web Fundamentals

## 1. Internet

The **Internet** is a global network that connects millions of computers and devices so they can communicate and share data with each other.

---

## 2. Network

A **network** is a group of connected devices that can communicate and exchange data with each other.

**Example:** Computers connected to the same Wi-Fi form a local network.

---

## 3. Client

A **client** is a device or application that requests a service or data from a server.

**Example:** A web browser is a client when it requests a webpage.

---

## 4. Server

A **server** is a computer or system that provides data, services, or resources to clients over a network.

**Example:** A web server sends webpage data when a browser requests it.

---

## 5. ISP

**ISP (Internet Service Provider)** is a company that provides users with access to the Internet.

**Example:** Airtel, Jio, and ACT provide Internet services.

---

## 6. Router

A **router** is a networking device that forwards data between different networks and helps devices communicate with the Internet.

**Example:** Your home Wi-Fi router connects your devices to your ISP and the Internet.

---

## 7. IP Address

An **IP address** is a numerical address used to identify a device on a network and help route data to the correct destination.

**Example:**

```text
192.168.1.10
```

---

## 8. IPv4

**IPv4 (Internet Protocol version 4)** is a protocol that uses 32-bit IP addresses to identify devices on a network.

An IPv4 address is written as four numbers separated by dots.

**Example:**

```text
192.168.1.10
```

---

## 9. Public IP

A **public IP address** is an IP address that identifies a network or device on the public Internet. It can be used to communicate with systems outside the local network.

---

## 10. Private IP

A **private IP address** is used to identify devices inside a local network. It is not directly reachable from the public Internet.

Common private IP ranges include:

```text
10.0.0.0 – 10.255.255.255
172.16.0.0 – 172.31.255.255
192.168.0.0 – 192.168.255.255
```

---

## 11. NAT

**NAT (Network Address Translation)** allows devices using private IP addresses to communicate with the Internet by translating private IP addresses into a public IP address.

**Example:**

```text
Private IP → Router/NAT → Public IP → Internet
```

---

## 12. Subnet

A **subnet (subnetwork)** is a smaller network created by dividing a larger IP network into smaller sections. It helps organize devices and manage network traffic efficiently.

---

## 13. Subnet Mask

A **subnet mask** determines which part of an IP address represents the network and which part represents the device.

**Example:**

```text
IP Address:  192.168.1.10
Subnet Mask: 255.255.255.0
```

---

## 14. DNS

**DNS (Domain Name System)** converts human-readable domain names into IP addresses that computers use to communicate.

**Example:**

```text
google.com → IP Address
```

---

## 15. HOSTS.TXT

**HOSTS.TXT** was an early system used to map domain names to IP addresses. Computers could check this file to find the IP address associated with a hostname before DNS became widely used.

**Example:**

```text
192.168.1.10    example.com
```

---

## 16. DNS Hierarchy

The **DNS hierarchy** is a tree-like structure used to organize domain names and resolve them into IP addresses.

The main levels are:

```text
Root
 ↓
Top-Level Domain (TLD)
 ↓
Domain
 ↓
Subdomain
```

**Example:**

```text
www.example.com
│   │       │
│   │       └── TLD
│   └────────── Domain
└────────────── Subdomain
```

---

## 17. How a Website Works

When you open a website, the browser and different network systems work together to retrieve and display the requested webpage.

### Overall Flow

```text
URL
 ↓
DNS
 ↓
IP Address
 ↓
Network connection
 ↓
TCP
 ↓
TLS
 ↓
HTTPS
 ↓
HTTP Request
 ↓
Google Server
 ↓
Backend/Application
 ↓
Database 
 ↓
HTTP Response
 ↓
Browser
```

### Flow Explanation

* **URL** — The browser uses the website's URL to know which resource to access.

* **DNS** — DNS converts the domain name in the URL into an IP address.

* **IP Address** — The IP address identifies the destination server.

* **TCP** — TCP establishes a reliable connection between the client and server.

* **TLS/HTTPS** — TLS encrypts the communication between the browser and server when HTTPS is used.

* **HTTP Request** — The browser sends an HTTP request asking the server for a resource.

* **Web Server** — The web server receives the request and handles the incoming connection.

* **Backend** — The backend processes the request and performs the required application logic.

* **Database** — The backend communicates with the database when data needs to be stored or retrieved.

* **HTTP Response** — The server sends the requested data and other information back to the browser.

* **Browser** — The browser receives the response and displays the website to the user.
