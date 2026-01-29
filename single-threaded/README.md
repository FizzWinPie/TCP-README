## 🌐 TCP Handshake Simulation (Client-Server Model)
This project demonstrates a simplified, single-threaded TCP handshake between a client and a server using raw sockets in C. The communication follows a 3-step numeric message protocol designed for learning low-level network programming.

## 🎬 Demo

![Single-threaded TCP Server Demo](singlethreaded-demo.gif)

## 🤝 Protocol Overview
Goal: Simulate a simple number-based handshake using TCP sockets.

Server Behavior
Receives HELLO X → prints to stdout

Sends HELLO X+1 back to client

Receives HELLO X+2 → prints to stdout and validates sequence

Client Behavior
Sends HELLO X to server

Receives HELLO X+1 → prints to stdout

Sends HELLO X+2 back to server

## 📁 File Structure
- `tcpclient.c` — TCP client implementation  
- `tcpserver.c` — Single-threaded TCP server  
- `helper.c` / `helper.h` — Shared utility functions  
- `Makefile` — For building the project

## 🧪 Example Usage
### 1. Compile the project
```bash
make
```

### 2. Run the server
```bash
./tcpserver 8000
```

### 3. In another terminal, run the client
```bash
./tcpclient 127.0.0.1 8000 1
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

## 🧠 Learning Objectives
Raw TCP socket programming using POSIX system calls

Manual client-server communication protocol

Safe buffer handling (recv, send, memory allocation)

Socket lifecycle: socket(), bind(), listen(), accept(), connect(), close()


### 🔒 Academic Note
This repository is private in accordance with University of Pennsylvania’s academic integrity policy to prevent reuse or plagiarism.
If you are a recruiter or interviewer and would like to see the source code or a live demo, I’m happy to provide it upon request.