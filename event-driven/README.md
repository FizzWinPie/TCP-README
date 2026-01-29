# 📡 Event-Driven TCP Protocol

This project implements an **event-driven, single-threaded TCP server** (`async-tcpserver`) that simulates a basic 3-way handshake with multiple clients concurrently.

Unlike the multi-threaded server, this server uses the `select()` system call to monitor multiple sockets without threads. It maintains per-client state in an array and handles interleaved client messages efficiently.

This server can handle interleaving and delays which are added to tcpclient.c

---

## 🎬 Demo

![Event-Driven TCP Server Demo](async-demo.gif)


## 📁 Project Layout

- `tcpclient.c` — TCP client implementation (with optional delays)
- `async-tcpserver.c` — Event-driven, single-threaded TCP server
- `helper.c` / `helper.h` — Shared utility functions
- `concurrent-requests.py` — Python script to simulate concurrent clients
- `Makefile` — Build instructions

---

## 🧪 Usage

### 1. Compile the project
```bash
make
```

### 2. Run the server
```bash
./async-tcpserver 8000
```

### 3. In another terminal, run the client
```bash
./tcpclient 127.0.0.1 8000 1
```

### 4. To simulate multiple concurrent clients, run:
```bash
python3 concurrent-requests.py 8000
```

## 🖥️ Expected Output
Server (stdout)
```bash
HELLO 1
HELLO 3
```

Client (stdout)
```bash
HELLO 2
```

Each client thread performs a simplified 3-way handshake, and the server responds to each concurrently. After running concurrent-requests.py, you should see 100 random HELLO handshakes on the server and across all clients. 

### 🔒 Academic Note
This repository is private in accordance with University of Pennsylvania’s academic integrity policy to prevent reuse or plagiarism.
If you are a recruiter or interviewer and would like to see the source code or a live demo, I’m happy to provide it upon request.