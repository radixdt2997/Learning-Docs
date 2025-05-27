# Chapter 3: RPC vs REST & HTTP/1.1 vs HTTP/2

---

## 📡 What is RPC?

- RPC (Remote Procedure Call) lets you call a function on another machine as if it's local.
- Uses a defined **interface (IDL)** to describe the available functions.
- Common in service-to-service communication (e.g., microservices).
- Often used with **binary formats** for better speed and efficiency.

---

## 🌐 What is REST?

- REST (Representational State Transfer) is a style of API built on top of **HTTP**.
- Uses **standard HTTP methods** like `GET`, `POST`, `PUT`, and `DELETE`.
- Works well with **web clients** (browsers, mobile apps).
- Uses **JSON** for data format, which is easy to read but heavier than binary.

---

## 🔁 RPC vs REST: Comparison

| Feature                 | RPC (e.g., gRPC)                                | REST (HTTP APIs)                            |
| ----------------------- | ----------------------------------------------- | ------------------------------------------- |
| 🔗 Protocol             | Custom (e.g., HTTP/2, TCP)                      | HTTP/1.1 or HTTP/2                          |
| 📦 Data Format          | Binary (e.g., Protocol Buffers)                 | Text-based (mostly JSON)                    |
| 📘 Interface Definition | Requires `.proto` or IDL                        | Defined by endpoint URLs and methods        |
| 🧠 Strong Typing        | Yes                                             | No (loosely typed)                          |
| 🚀 Performance          | High (compact binary, less overhead)            | Slower due to larger payloads               |
| 🌐 Browser Friendly     | No (not directly usable in browsers)            | Yes                                         |
| 📂 Caching              | No (needs manual setup)                         | Built-in HTTP caching support               |
| 🔁 Streaming            | Supported (unary, server/client, bidirectional) | Limited (long polling or chunked responses) |
| 🛠 Tooling               | Code generation for many languages              | Manual request/response handling            |
| 🔒 Authentication       | Custom (e.g., TLS, tokens)                      | Built-in options (e.g., OAuth2 via headers) |

---

## 🧠 When to Use RPC or REST?

### ✅ Use **RPC** when:

- You need **high performance** and low latency.
- Services are internal (e.g., between microservices).
- You want **typed APIs** with code generation support.

### ✅ Use **REST** when:

- Your API needs to be **public or consumed by web apps**.
- You prefer simpler setup and **human-readable data**.
- You need **standard HTTP features** like caching and status codes.

---

## 🌐 HTTP/1.1 vs ⚡ HTTP/2

Both REST and RPC can use HTTP as a transport layer. Understanding the versions of HTTP helps in performance tuning.

---

## 🔍 What is HTTP/1.1?

- Introduced in 1997.
- Uses **text-based** messages (headers + body).
- Allows **one request at a time per connection**.
- Needs **multiple connections** to load resources in parallel (e.g., images, scripts).
- Suffers from **head-of-line blocking** (one slow request can block others).

---

## ⚡ What is HTTP/2?

- Introduced in 2015.
- Uses a **binary framing layer** for compact and faster messages.
- Supports **multiplexing**: multiple requests on a single connection.
- Reduces overhead and latency compared to HTTP/1.1.
- Includes features like:
  - **Header compression**
  - **Server push**
  - **Stream prioritization**

---

## 🔁 HTTP/1.1 vs HTTP/2: Comparison

| Feature               | HTTP/1.1                   | HTTP/2                                |
| --------------------- | -------------------------- | ------------------------------------- |
| 🔄 Request Handling   | One request per connection | Multiple requests over one connection |
| 🔠 Format             | Text-based                 | Binary                                |
| 📉 Header Compression | No                         | Yes (HPACK)                           |
| 📤 Server Push        | No                         | Yes                                   |
| 🚧 Head-of-Line Block | Yes                        | No (requests handled in parallel)     |
| ⚙️ Prioritization     | No                         | Yes                                   |
| 🔗 Connection Use     | Needs multiple connections | One connection handles everything     |

---

## 📚 Summary

### RPC

- High-performance, binary protocol
- Best for internal services
- Requires more setup and tooling

### REST

- Simpler, human-readable
- Better for external APIs and web usage
- Uses standard HTTP features

### HTTP/2

- Faster and more efficient than HTTP/1.1
- Essential for performance in both REST and modern RPC (like gRPC)

---

➡️ Next: Move on to `4_GRPC_INTRO.md` to start learning about **gRPC** — a high-performance, modern RPC framework built on HTTP/2 and Protocol Buffers.
