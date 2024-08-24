# Real-Time Chat Application
## Overview
This project implements a basic real-time chat application using TCP sockets in C. The application consists of a server and multiple clients. The server manages multiple client connections and facilitates the exchange of messages between clients.

## Features
Server: Listens for incoming client connections, handles multiple clients concurrently, and broadcasts messages from one client to all others.
Client: Connects to the server, sends messages, and displays messages received from other clients in real time.
## Requirements
A C compiler (e.g., gcc)
A POSIX-compatible environment (e.g., Linux or macOS)
## Getting Started
### 1. Compile the Server and Client
Use the following commands to compile the server and client programs:

```bash
gcc -o server server.c -lpthread
gcc -o client client.c -lpthread
```

### 2. Run the Server
In a terminal, start the server:
```bash
./server
```

The server will begin listening on port 8080 by default.

### 3. Run the Clients
In one or more additional terminals, start the clients:

```bash
./client
```

Each client will connect to the server, enabling them to send and receive messages from other clients.

## Code Explanation
Server Code (server.c)
- Socket Creation: The server creates a socket for communication.
- Binding: The server binds the socket to an address and port.
- Listening: The server listens for incoming client connections.
- Client Handling: For each client connection, a new thread is created to manage communication.
- Message Broadcasting: Messages received from one client are broadcast to all other connected clients.
  
Client Code (client.c)
- Socket Creation: The client creates a socket for communication.
- Connecting: The client connects to the server using the specified address and port.
- Message Sending: The client reads input from the user and sends it to the server.
- Message Receiving: The client receives messages from the server and displays them.

## Configuration
By default, the server listens on port 8080 and clients connect to 127.0.0.1 (localhost). These settings can be modified in the code if needed.
