# Chapter 2: How RPC Works (Behind the Scenes)

Now that you understand what RPC is, let’s go a bit deeper and explore **how it actually works**, what happens under the hood, and some pros and cons.

---

## 🛠️ What Does RPC Actually Do?

RPC is often used to build **distributed systems**, where different parts of the system run on different machines but still talk to each other like they’re on the same system.

- RPC allows you to **call a function on another computer** without worrying about the network details.
- Although RPC looks like a transport protocol, it’s actually a way to allow programs to **communicate between processes** (called Inter-Process Communication or IPC).

---

## 🧩 What is a Stub in RPC?

A **stub** is like a translator between your code and the remote system. It does a lot of work behind the scenes.

### There are two stubs:

- **Client Stub**: Pretends to be the function you’re calling.
- **Server Stub**: Receives the request and calls the actual function on the server.

> 🧠 Think of a stub like a **messenger** that knows how to pack, send, and unpack the message between two people who speak different languages.

---

## 🔁 RPC Workflow (Step-by-Step)

Here’s what happens when a client calls a remote function:

1. **Client Code Calls Function**  
   The client calls the function like it’s a regular local function.

2. **Marshaling the Data (Packing Parameters)**  
   The **client stub** converts (marshals) the function name and parameters into a format that can be sent over the network.

3. **Sending the Request**  
   The client’s OS sends this message over the network to the server.

4. **Server Receives the Request**  
   The **server stub** gets the message, unpacks (unmarshals) it, and calls the actual function.

5. **Function Executes on Server**  
   The real function runs on the server and produces a result.

6. **Response is Sent Back**  
   The server stub marshals the return value and sends it back to the client.

7. **Client Receives the Response**  
   The client stub unmarshals the response and gives it to the calling code, as if it were a local function.

> ✅ All this happens under the hood, so the developer just sees a simple function call!

---

## ⚙️ Types of RPC

| Type         | Description                                                             |
| ------------ | ----------------------------------------------------------------------- |
| Synchronous  | Client waits for server to finish and return the result (most common)   |
| Non-blocking | Client sends a request and keeps working, doesn’t wait for response     |
| Batch Mode   | Client sends multiple requests together in one go                       |
| Broadcast    | Client sends the same request to many servers at once                   |
| Callback     | Client sends a request, and the server later calls back with the result |

---

## 🔄 RPC in Modern Applications

RPC can be adapted to fit other programming models, such as **microservices**. Modern RPC frameworks like **gRPC** support high-performance communication, language interoperability, and streaming.

---

## ✅ Advantages of RPC

- 🌍 **Works locally or across networks**.
- 🧵 **Supports threads and processes**.
- 🧼 **Hides networking details** from the developer.
- ⚡ **Efficient**: Skips some of the heavier protocol layers.

---

## ⚠️ Disadvantages of RPC

- 🧩 **Complex environment**: Server and client run in different environments with different resources.
- 📉 **Not ideal for large data transfers**.
- 🔄 **Risk of failure**: Since it's dependent on network and remote systems.
- 🔒 **Less flexible** than RESTful APIs for some use cases.

---

## 📚 Summary

| Concept          | Description                                   |
| ---------------- | --------------------------------------------- |
| Stub             | Helper code that sends and receives RPC calls |
| Marshaling       | Packing function parameters into a message    |
| Unmarshaling     | Unpacking received parameters                 |
| Synchronous Call | Waits for result                              |
| Non-blocking     | Doesn’t wait, keeps working                   |

---

🧭 You're now ready to explore **gRPC**, a modern and powerful RPC framework used in cloud-native and microservices architectures.

➡️ Go to: `3_GRPC_INTRO.md` to begin your journey into gRPC!
