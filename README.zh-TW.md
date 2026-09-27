# 線上多人德州撲克平台原始碼

**C++ / Tars 房間服務，涵蓋私人房、快速場、AOF、短牌、SNG、MTT/淘汰賽、保險、牌譜與俱樂部基金流程。**

[简体中文](README.md) · [繁體中文](README.zh-TW.md) · [English](README.en.md) · [產品網站](https://masterai-top.github.io/Online-Texas-Holdem-Poker-Platform/zh-tw/)

![線上德州撲克牌桌與操作介面](docs/assets/images/poker-table-action.jpg)

## 產品定位

此倉庫展示線上多人德州撲克房間與牌桌服務的核心程式結構。`Room.cpp`、`Player.h`、`RoomServant.tars`、訊息處理程式與遊戲模組，呈現配對、入桌、下注、旁觀、離線到牌局記錄的服務端流程。

它適合評估或二次開發線上德州撲克服務、私人局、俱樂部房間、SNG 與 MTT 賽事房間。完整上線仍需依實際環境接入設定、資料庫、閘道、支付、風控與客戶端。

## 已驗證玩法與功能

- **私人房 / 好友局**：私人房類型、房主管理、買入與結算資料。
- **快速開始、AOF、短牌**：程式中有對應的專用桌台管理流程。
- **SNG、MTT / 淘汰賽**：報名、排名、淘汰與獎池相關狀態。
- **牌桌操作**：坐下、站起、下注、買入、延時、自動操作與公共牌顯示。
- **保險與多次發牌**：保險流程及 Run It Twice 相關訊息。
- **牌譜與結果**：回放、收藏、行動軌跡、房間結果與積分記錄。
- **俱樂部基金**：房間資訊、基金發放、流水與管理介面。
- **訂單介面**：iOS 與 Google Play 訂單建立、驗證與消耗驗證。

## 產品畫面

| 即時牌桌 | 俱樂部管理 |
|---|---|
| ![九人桌、保險、GPS/IP及操作](docs/assets/images/poker-table-overview.jpg) | ![成員、管理員、聯盟、基金及統計](docs/assets/images/club-management.jpg) |

| 手牌記錄 | 房間結果 |
|---|---|
| ![翻牌前及攤牌行動回放](docs/assets/images/hand-history.jpg) | ![買入、積分、旁觀與保險池](docs/assets/images/room-results.jpg) |

![房主買入倍數、行動時間、暫停與解散](docs/assets/images/room-owner-controls.jpg)

## 玩家流程

1. 玩家由大廳進入公開配對、俱樂部或私人房。
2. 房間服務記錄配對、入座、旁觀、離線與重連狀態。
3. 玩家買入並進行下注、延時、自動操作與保險選擇。
4. 牌局完成後產生結果、牌譜與俱樂部資金記錄。
5. SNG/MTT 繼續處理報名、排名、淘汰及獎池流程。

## C++ / Tars 架構

```text
客戶端 / 閘道
      ↓
RoomServant（房間請求、離線與通知）
      ↓
Room / PlayerMng / TableManager
      ↓
Quick · AOF · Short Deck · Private · SNG · MTT
      ↓
設定 / 資料庫代理 / 日誌 / 活動 / 大廳等外部服務
```

關鍵檔案包括 `GameDataDef.h`、`Room.cpp`、`Player.h`、`message/onclientmessage.cpp`、`RoomServant.tars` 與 `OrderServant.tars`。遊戲玩法以動態 `.so` 模組載入，方便按房間類型分離實作。

## 多語言與部署範圍

產品畫面顯示簡體中文、繁體中文、English、한국어 與 Bahasa Indonesia。此倉庫主要展示服務與協定程式；正式部署仍需匹配的 Tars 環境、設定中心、資料庫/快取、閘道、客戶端、支付憑證、監控與安全配置。

![多語言設定](docs/assets/images/language-settings.jpg)

## 聯絡方式

- Telegram：[@xuzongbin001](https://t.me/xuzongbin001)
- Email：[masterai918@gmail.com](mailto:masterai918@gmail.com)

> 請遵守所在地關於軟體、資料、支付與遊戲營運的法律規範。本說明僅供技術評估與合規開發。
