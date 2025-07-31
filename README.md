### Note to Recruiter:
The code for this repository is private due to an agreement with the University of Pennsylvania, intended to prevent academic dishonesty. However, I’m happy to share the code and a live demo upon request during the interview process.
Please find the README and a recorded demo attached for general project information.


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

## 🛠️ Build Instructions are provided in the README file of each implementation
