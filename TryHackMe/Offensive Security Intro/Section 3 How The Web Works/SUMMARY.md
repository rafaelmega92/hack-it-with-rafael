# 🌐 TryHackMe: How the Web Works - Notes

This document summarizes the key concepts from the **"How the Web Works"** section of the TryHackMe module. Topics include DNS, HTTP, websites, web servers, and modern web infrastructure.

---

## 📡 DNS in Detail

### Task 1: What is DNS?
- DNS (Domain Name System) allows users to access websites without needing to remember IP addresses.
- Every internet-connected device has a unique IP address.

### Task 2: Domain Hierarchy
- **TLD**: Top-Level Domain (e.g., .com, .edu, .gov)
  - gTLD (Generic) — purpose-driven
  - ccTLD (Country Code) — geographically defined
- **Second-Level Domain**: The website name (e.g., `google` in google.com).
- **Subdomains**: Sit to the left of the domain name (e.g., `admin` in admin.tryhackme.com).
- Domain names must follow character and length rules (e.g., max 253 characters).

### Task 3: Record Types
- **A**: Maps to IPv4
- **AAAA**: Maps to IPv6
- **CNAME**: Points to another domain
- **MX**: Handles email
- **TXT**: Stores arbitrary text

### Task 4: Making a Request
1. Local cache check → Recursive DNS Server
2. If not cached, query travels through:
   - **Root servers** → **TLD servers** → **Authoritative nameservers**
3. Authoritative DNS provides final response → Cached → Delivered to client

---

## 📬 HTTP in Detail

### Task 1: What is HTTP(S)?
- **HTTP**: Protocol for transmitting web data
- **HTTPS**: Secure version with encryption and server authentication

### Task 2: Requests and Responses
- **URL Components**:
  - Scheme, User, Host, Port, Path, Query String, Fragment
- A simple GET request can be: `GET / HTTP/1.1`

### Task 3: HTTP Methods
- **GET**: Retrieve info
- **POST**: Submit data
- **PUT**: Update data
- **DELETE**: Remove data

### Task 4: HTTP Status Codes
- **100–199**: Informational
- **200–299**: Success
- **300–399**: Redirection
- **400–499**: Client errors
- **500–599**: Server errors
- Common examples:
  - `200 OK`, `404 Not Found`, `500 Internal Server Error`, `503 Service Unavailable`

### Task 5: Headers
- **Request Headers**: Host, User-Agent, Content-Length, Accept-Encoding, Cookie
- **Response Headers**: Set-Cookie, Cache-Control, Content-Type, Content-Encoding

### Task 6: Cookies
- Small data stored on the client from a Set-Cookie header
- Help websites track sessions due to HTTP's statelessness

---

## 🖥️ How Websites Work

### Task 1: Overview
- **Front End**: Browser-side rendering
- **Back End**: Server-side processing

### Task 2: HTML
- Structure of a webpage using tags:
  - `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`, `<h1>`, `<p>`
- Elements can include **attributes**: `id`, `class`, etc.

### Task 3: JavaScript
- Adds interactivity to pages
- Can be embedded via `<script>` or loaded externally via `src`

### Task 4: Sensitive Data Exposure
- Exposing clear-text sensitive data (like credentials) in frontend source code

### Task 5: HTML Injection
- Occurs when user input is improperly filtered and injected into the page
- Emphasizes importance of input sanitization

---

## 🧩 Putting it All Together

### Task 1: Other Components
- **Load Balancers**:
  - Distribute requests across multiple servers
  - Provide failover and traffic balancing (e.g., round-robin, weighted)
- **CDNs**:
  - Host static files across global servers
  - Reduce server load and latency
- **Databases**:
  - Store and serve data for websites (MySQL, MongoDB, etc.)
- **WAF (Web Application Firewall)**:
  - Filters and monitors HTTP requests
  - Protects against attacks (e.g., DoS)

### Task 2: How Web Servers Work
- **Web Servers**:
  - Serve content using HTTP (Apache, Nginx, IIS, NodeJS)
- **Virtual Hosts**:
  - Host multiple domains on the same server
- **Static vs Dynamic Content**:
  - Static: HTML, images, CSS
  - Dynamic: Content rendered per request (e.g., blog articles)
- **Scripting/Backend Languages**:
  - PHP, Python, Ruby, NodeJS, etc. — handle logic, database interaction, and API calls

---

📝 *Follow my progress on [GitHub](https://github.com/yourusername) as I complete more TryHackMe modules!*
