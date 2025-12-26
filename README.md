# Exploring Redis From Scratch: Core Features for a Local Environment 🧠⚡

A Redis-inspired in-memory key-value store explore from scratch using **Python**, focusing on core system design concepts such as **TCP networking**, **event-driven architecture**, **single-threaded concurrency**, **TTL expiration**, **persistence mechanisms (AOF & RDB)**, **Publish/Subscribe System**, as well as **Python GIL Concept**.

## 📚 Index

1. [Building a Simple TCP Server in Python](#https://github.com/dear-mahmud-bd/explore-redis-from-scratch/tree/main/Simple_TCP)
2. [Single-Threaded TCP Server with Event Loop](#https://github.com/dear-mahmud-bd/explore-redis-from-scratch/tree/main/Single_Threaded_TCP)
3. [In-Memory Storage with TTL & Background Key Expiration](#https://github.com/dear-mahmud-bd/explore-redis-from-scratch/tree/main/In_Memory_Storage_with_TTL)
4. [Redis AOF Persistence](#https://github.com/dear-mahmud-bd/explore-redis-from-scratch/tree/main/Redis-AOF_Persistence)
5. [Redis RDB Persistence](#https://github.com/dear-mahmud-bd/explore-redis-from-scratch/tree/main/Redis-RDB_Persistence)
6. [Explore Redis Native Data Structures](#https://github.com/dear-mahmud-bd/explore-redis-from-scratch/tree/main/Explore-Redis_Native-DS)
7. [Redis Publish/Subscribe Messaging System](#https://github.com/dear-mahmud-bd/explore-redis-from-scratch/tree/main/Pub-Sub_Messaging_System)

---

This project helped me deeply understand how Redis works internally by implementing its core components from the ground up.

---

## 🚀 Features

### 🔌 Networking

- Custom TCP server using Python `socket`
- Redis-compatible port (`6379`)
- Supports multiple concurrent clients
- Non-blocking I/O using `select()` (event loop)

### 🧵 Architecture

- **Single-threaded event loop** (Redis-style)
- No locks or race conditions
- Efficient connection multiplexing
- Command pipelining support

### 🗄️ Data Storage

- In-memory key-value store
- O(1) average-time operations
- Type-aware storage
- Shared state across all clients

### ⏱️ TTL & Expiration

- Commands: `EXPIRE`, `EXPIREAT`, `TTL`, `PTTL`, `PERSIST`
- Lazy expiration (on access)
- Active expiration (background cleanup)
- Probabilistic cleanup strategy (Redis-like)

### 💾 Persistence

#### Append-Only File (AOF)

- Logs every write command
- Supports fsync policies:
  - `always`
  - `everysec`
  - `no`
- Background AOF rewrite (`BGREWRITEAOF`)
- Crash-safe recovery

#### RDB Snapshots

- Binary snapshot persistence
- Background saving (`BGSAVE`)
- Copy-on-write friendly design
- Data recovery on restart

---

## ▶️ Getting Started

#### Run the Server

Navigate to the project directory and start the server:

```bash
python main.py
```

#### Connect as a Client

Use `telnet` to connect to the Redis-like server:

```bash
telnet localhost 6379
```

## 🧪 Supported Commands

```text
PING
ECHO
SET / GET / DEL
EXISTS
KEYS
TYPE
FLUSHALL

EXPIRE / EXPIREAT
TTL / PTTL
PERSIST

INFO
BGREWRITEAOF
```
