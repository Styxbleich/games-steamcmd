# Windrose

### Authors / Maintainers

- [Styxbleich](https://github.com/Styxbleich)

## Description

Windrose is an Early Access PvE co-op pirate survival game built on Unreal Engine 5. The dedicated server binary is Windows-only and runs via Proton on Linux. Installed anonymously via SteamCMD (App ID `4129620`).

> **Important:** Players connect using an **invite code**, NOT by IP:port. After the server is marked running in the console, share the `InviteCode` with your crew via **Play → Connect to Server → paste code**.

## Features

- Configurable server name, invite code, max players, and optional password
- Auto-update via SteamCMD on startup (toggleable)
- World progress saved automatically via RocksDB and persists between restarts
- Full server log streamed to the Pelican console

## Server Ports

| Port | Default | Protocol | Note |
|------|---------|----------|------|
| Game | 7777 | UDP | Must be set as Primary Allocation |
| Query | 7778 | UDP | Must be added as an Additional Allocation |

> Windrose uses P2P NAT punch-through for player connections. These ports do not need to be forwarded for players to connect, but **both must be allocated in Pelican** or the server will fail to register with the Windrose relay servers.

## Variables

| Variable | Default | Description |
|----------|---------|-------------|
| Server Name | `Windrose1` | Display name shown in `ServerDescription.json` |
| Invite Code | `Server01` | Code players use to connect. Min 6 chars, alphanumeric. |
| Max Players | `4` | Max simultaneous players (1–8). Developers recommend 4 or fewer during Early Access. |
| Password Protected | `false` | Set to `true` to require a password to join. |
| Server Password | *(blank)* | Only used if Password Protected is `true`. |
| Update on Start | `1` | Set to `1` to check for updates on every start, `0` to skip. |

## Notes

- World saves are stored at `R5/Saved/SaveProfiles/Default/RocksDB/` — SSD storage is strongly recommended.
- Xalia-related errors in the console on startup are harmless and do not affect server operation.
- This is an Early Access title. Stability may vary between game updates.

## Developer Dedicated Server Guide

The Developers have also published a guide for using a dedicated server found here (https://playwindrose.com/dedicated-server-guide/#wsg-setup)