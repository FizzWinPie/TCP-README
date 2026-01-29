# 🐚 TCP Suite: Client-Server Projects in C

This repository contains a series of progressively advanced TCP networking projects built in C. Each part builds on the previous to demonstrate different techniques for managing socket connections, concurrency, and event-driven I/O.

---

## 📦 Project Overview

| Folder Name                | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
|  single-threaded       | Simple **single-client** TCP server that performs a 3-way handshake.        |
| multi-threaded   | **Multi-threaded** TCP server that handles multiple clients concurrently.   |
| event-driven   | **Event-driven, single-threaded** TCP server using `select()` to scale.     |

---

## 🎬 Demos

### Part 1: Single-threaded Server
![Single-threaded TCP Server Demo](single-threaded/singlethreaded-demo.gif)
<p align="left"> <i><b>Figure 1.</b> Basic single-threaded architecture handling one client at a time with 3-way handshake validation.</i> </p>

**Architecture:** Sequential request processing in a single thread. This implementation validates a 3-way handshake (`HELLO 1` → `HELLO 2` → `HELLO 3`) and rejects invalid handshakes. Simple and lightweight, but limited to one client connection at a time.

<br/>

### Part 2: Multi-threaded Server
![Multi-threaded TCP Server Demo](multi-threaded/multithreaded-demo.gif)
<p align="left"> <i><b>Figure 2.</b> Multi-threaded architecture utilizing 1:1 thread-to-connection mapping for parallel request processing.</i> </p>

**Architecture:** Scalable concurrency via POSIX threads. This implementation supports 100+ simultaneous handshakes by offloading each connection to a dedicated worker thread, ensuring high throughput at the cost of increased memory footprint.

<br/>

### Part 3: Event-driven Server
![Event-Driven TCP Server Demo](event-driven/async-demo.gif)
<p align="left"> <i><b>Figure 3.</b> Event-driven, single-threaded architecture using I/O multiplexing for efficient multi-client handling.</i> </p>

**Architecture:** Single-threaded concurrency using `select()` for I/O multiplexing. This implementation supports 100+ concurrent clients without thread overhead by maintaining per-client state in a static array and efficiently managing multiple socket descriptors in one event loop.

---

## 🚀 Features by Part

### ✅ single-threaded: 
- Handles one client at a time
- Validates a 3-message handshake:
  - `HELLO 1` → `HELLO 2` → `HELLO 3`
- Rejects invalid handshakes

### ✅ multi-threaded:
- Spawns a **new thread** for each client
- Thread-safe state handling
- Allows multiple simultaneous handshakes
- Supports 100+ concurrent clients without threading

### ✅ event-driven:
- Uses `select()` for I/O multiplexing
- Fully **single-threaded**
- Tracks state per client in a static array
- Supports 100+ concurrent clients without threading

---

### Note to Recruiter:
The code for this repository is private due to an agreement with the University of Pennsylvania, intended to prevent academic dishonesty. However, I’m happy to share the code and a live demo upon request during the interview process.
Please find the README and a recorded demo attached for general project information.
