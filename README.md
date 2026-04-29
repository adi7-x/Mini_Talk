<h1 align="center">📡 Mini_Talk</h1>

<p align="center">
  <strong>UNIX Signal-Based Messaging — 42 School</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=black"/>
  <img src="https://img.shields.io/badge/42-000000?style=for-the-badge&logo=42&logoColor=white"/>
  <img src="https://img.shields.io/badge/UNIX_Signals-333333?style=for-the-badge"/>
</p>

---

## About

A client-server communication program that exchanges messages using only **UNIX signals** (`SIGUSR1` and `SIGUSR2`). Data is transmitted bit by bit — demonstrating deep understanding of inter-process communication, signal handling, and binary data encoding.

## How It Works

```
Client                          Server
  │                               │
  │  SIGUSR1 (bit = 1)           │
  ├──────────────────────────────→│
  │  SIGUSR2 (bit = 0)           │
  ├──────────────────────────────→│
  │         ...                   │
  │  (8 signals = 1 character)   │
  │                               │ → Reconstructs & prints character
```

## Usage

```bash
make

# Terminal 1: Start the server
./server
# Prints PID, e.g.: Server PID: 12345

# Terminal 2: Send a message
./client 12345 "Hello from Mini_Talk!"
```

## Key Concepts

- **UNIX Signals** — `SIGUSR1` / `SIGUSR2` as binary data carriers
- **Bitwise operations** — Encoding/decoding characters bit by bit
- **Process communication** — Client/server architecture via PIDs
- **Signal reliability** — Handling signal delivery with acknowledgment

---

<p align="center"><sub>42 School · Common Core · UNIX Signals & IPC</sub></p>
