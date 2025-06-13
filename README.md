# 🌐 Arcadia Net

Arcadia Net is the multiplayer backbone of the Arcadia Engine.

It defines a lightweight, pluggable communication model for building deterministic multiplayer games using client-server or peer-authority models.

---

## 🔗 Goals

- Simple interface: `ArcadiaConnection`
- Syncable: Position, state, and component deltas
- Predictive: Support for client prediction and rollback (planned)
- Agnostic: Works with TCP, UDP, WebSocket transports

---

## 🧱 Architecture

```plaintext
[Client]
 └── ArcadiaClient
       └── ArcadiaConnection (send/receive intents)

[Server]
 └── ArcadiaServer
       └── Simulation → Broadcast WorldDiffs
```

---

## 📦 Core Types

| Class | Purpose |
|-------|---------|
| `ArcadiaConnection` | Base network interface |
| `ArcadiaClient` | Player-side socket connection |
| `ArcadiaServer` | Tick authority + diff broadcaster |
| `SyncPacket` | Deltas between ticks (planned) |

---

## 📜 Specs

See [`arcadia-server-authority.md`](https://github.com/arcadia-engine/arcadia-planning/blob/main/design-docs/arcadia-server-authority.md)

---

## 🛤️ Roadmap

- [ ] ArcadiaConnection base classes
- [ ] Local loopback client/server
- [ ] JSON sync packet format
- [ ] Desync detector (optional)
