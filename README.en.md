# Online Multiplayer Texas Hold'em Poker Platform

**A C++ / Tars room-service codebase covering private tables, Quick Start, AOF, Short Deck, SNG, MTT/knockout flows, insurance, hand history and club-fund operations.**

[简体中文](README.md) · [繁體中文](README.zh-TW.md) · [English](README.en.md) · [Product site](https://masterai-top.github.io/Online-Texas-Holdem-Poker-Platform/en/)

![Online Texas Holdem table and player controls](docs/assets/images/poker-table-action.jpg)

## What this repository contains

This repository presents the core room and table services of an online multiplayer Texas Hold'em platform. Files such as `Room.cpp`, `Player.h`, `RoomServant.tars`, the client-message handlers and game modules show server-side flows for matching, seating, betting, spectating, disconnect recovery and hand records.

It is useful for evaluating or extending an online poker server, private poker tables, club rooms, SNG and MTT tournament rooms. A production launch still requires compatible configuration, database, gateway, payment, security, compliance and client components.

## Verified modes and features

- **Private tables:** private-room type, owner controls, buy-ins and settlement data.
- **Quick Start, AOF and Short Deck:** dedicated table-manager paths in the room service.
- **SNG and MTT/knockout:** registration, rank and elimination states plus prize-pool interfaces.
- **Table actions:** sit/stand, betting, buy-in, time extension, auto-play and board display.
- **Insurance and multiple runs:** insurance requests and Run It Twice-related messages.
- **Hand history:** replay, favorites, action history and room-result collection.
- **Club operations:** club-room data, member-management screens, fund issuance and ledgers.
- **Order APIs:** order generation, validation and consumption checks for iOS and Google Play.

## Product screenshots

| Live multiplayer table | Club operations |
|---|---|
| ![Nine-seat table, insurance, GPS IP and actions](docs/assets/images/poker-table-overview.jpg) | ![Members, admins, league, funds and statistics](docs/assets/images/club-management.jpg) |

| Hand replay | Room results |
|---|---|
| ![Preflop and showdown action replay](docs/assets/images/hand-history.jpg) | ![Buy-ins, points, spectators and insurance pool](docs/assets/images/room-results.jpg) |

![Room-owner controls for rebuy, action time, pause and dissolve](docs/assets/images/room-owner-controls.jpg)

## Player journey

1. A player enters public matching, a club room or a private table from the lobby.
2. The room service tracks matching, seating, watching, disconnect and re-entry states.
3. After buying in, players bet and may use time extension, auto-play and insurance features.
4. The completed hand produces results, replay data and applicable club-fund records.
5. SNG/MTT rooms continue with registration, rankings, eliminations and prize-pool flows.

## C++ / Tars architecture

```text
Client / Gateway
      ↓
RoomServant (room requests, offline handling and notifications)
      ↓
Room / PlayerMng / TableManager
      ↓
Quick · AOF · Short Deck · Private · SNG · MTT
      ↓
Configuration / database proxy / logs / activity / lobby services
```

Key evidence includes `GameDataDef.h`, `Room.cpp`, `Player.h`, `message/onclientmessage.cpp`, `RoomServant.tars` and `OrderServant.tars`. Game variants can be loaded through dynamic `.so` modules. Robot and decision interfaces exist, but they should not be represented as a complete commercial poker-AI product.

## Languages and deployment scope

The product screenshot exposes Simplified Chinese, Traditional Chinese, English, Korean and Indonesian choices. This repository focuses on room services and protocols; deployment normally also requires a compatible Tars environment, configuration service, database/cache, gateway, client apps, payment credentials, monitoring and security controls.

![Multilingual settings](docs/assets/images/language-settings.jpg)

## Contact

- Telegram: [@xuzongbin001](https://t.me/xuzongbin001)
- Email: [masterai918@gmail.com](mailto:masterai918@gmail.com)

> Use the software only in compliance with local laws governing software, data, payments and gaming operations. This material is for technical evaluation and lawful development.
