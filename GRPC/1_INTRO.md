# Introduction to RPC (Remote Procedure Call)

## 🌐 What is RPC?

Remote Procedure Call (RPC) is a way for a program on one computer to call (invoke) a function that exists on another computer—**just like calling a local function**.

- It hides the complexity of networking.
- The caller doesn't need to worry about how the message is sent or received.
- Commonly used in **client-server applications**.

> 🧠 Think of it like making a phone call to your friend to ask them to do something for you.

---

## 🧱 How Does RPC Work?

1. A **client** makes a request to run a function.
2. The request is sent over the network to the **server**.
3. The server executes the function and sends back the result.
4. The client receives the result as if the function ran locally.

> Client (calls function) --> Network --> Server (runs function) --> Network --> Client (gets result)

---

## ⚙️ Key Features of RPC

- **Synchronous by default**: The client waits until it gets a response.
- **Client-Server Model**: One side requests, the other responds.
- **Language Agnostic**: Uses an **Interface Definition Language (IDL)** to describe the functions.
- **Cross-platform**: Works across Windows, Linux, macOS, etc.

---

## 🧩 What is IDL?

IDL (Interface Definition Language) is used to define the structure of RPC calls. It describes:

- The available functions (what can be called remotely)
- The input parameters
- The output data

> 🛠 This makes sure both client and server understand each other, even if they’re written in different programming languages.

---

## 📦 Why Use RPC?

- Makes it easy to build **distributed applications**
- Hides network communication details
- Improves modularity by splitting systems into services
- Used in many frameworks like **gRPC**, **Apache Thrift**, and more

---

## 📚 Summary

| Term           | Description                                        |
| -------------- | -------------------------------------------------- |
| RPC            | Call a function on another machine like it’s local |
| Client         | Requests a service                                 |
| Server         | Provides the service                               |
| IDL            | Defines the API (what functions are available)     |
| Cross-platform | Works across different operating systems           |

---

✅ Now that you understand what RPC is, you're ready to dive into **gRPC**—a modern, efficient RPC framework built on top of HTTP/2 and Protocol Buffers.

➡️ Go to: `2_RPC_WORKFLOW.md` to learn what gRPC is and how it improves on traditional RPC.
