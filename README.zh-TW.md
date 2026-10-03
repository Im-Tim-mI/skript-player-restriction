# 玩家限制系統

[English](README.md) | **繁體中文**

「凍結」型管理工具：被限制的玩家仍可登入與聊天，但無法建築、破壞、互動、攻擊、開容器、騎乘、睡覺或使用指令。可用名稱或 UUID 操作，支援名稱以 `.` 開頭的基岩版玩家。

> 本儲存庫包含同一個腳本的兩個版本：**繁體中文（zh-TW）** 是作者伺服器實際使用的原始版本；**English** 為完整英文翻譯版（指令、訊息與變數名稱皆為英文），功能相同。

## 功能特色

- 可用玩家名稱（在線或離線）或 UUID 限制，並記錄原因、執行者與時間
- 限制、解除限制及被限制玩家登入時全服廣播
- 禁止放置／破壞方塊、點擊、攻擊、丟棄、撿取、開啟容器、射擊、騎乘、睡床、踩踏耕地與使用任何指令
- 同時把玩家加入 LuckPerms 群組 `frozen`
- 提供查詢、列表、清理與強制移除等管理工具

## 需求

- [Paper](https://papermc.io/) 伺服器（開發環境 Paper 26.2 / Minecraft 26.2）
- [Skript](https://github.com/SkriptLang/Skript)（開發環境 2.16.2）
- [skript-reflect](https://github.com/SkriptLang/skript-reflect)（開發環境 2.6.3）（防止踩踏耕地）
- [LuckPerms](https://luckperms.net/)（群組 `frozen`）

## 安裝

1. 先安裝[需求](#需求)中列出的插件。
2. 下載**其中一個**版本：

   | 版本 | 檔案 |
   |---|---|
   | 繁體中文（原始版本） | [`zh-TW/玩家限制系統.sk`](zh-TW/%E7%8E%A9%E5%AE%B6%E9%99%90%E5%88%B6%E7%B3%BB%E7%B5%B1.sk) |
   | English（英文） | [`en/player-restriction.sk`](en/player-restriction.sk) |

3. 把 `.sk` 檔案放進伺服器的 `plugins/Skript/scripts/`。
4. 執行 `/sk reload 玩家限制系統`（請換成你放入的檔名），或重新啟動伺服器。

> [!IMPORTANT]
> **只能安裝其中一個版本。** 兩個版本是同一個腳本的不同語言，同時載入會互相衝突或重複執行。

## 指令

| 指令（中文版） | 英文版 | 說明 | 權限 |
|---|---|---|---|
| `/限制 <玩家名稱> <限制原因>` | `/restrict <player> <reason>` | 限制玩家 | OP |
| `/限制uuid <UUID> <限制原因>` | `/restrictuuid <uuid> <reason>` | 以 UUID 限制 | OP |
| `/解除限制 <玩家名稱>` | `/unrestrict <player>` | 解除限制 | OP |
| `/解除限制uuid <UUID>` | `/unrestrictuuid <uuid>` | 以 UUID 解除限制 | OP |
| `/限制狀態 <玩家名稱或UUID>` | `/restrictstatus <player or uuid>` | 查看限制資訊 | OP |
| `/限制列表` | `/restrictlist` | 列出被限制的玩家 | OP |
| `/限制清理` | `/restrictcleanup` | 清理重複與無效資料 | OP |
| `/強制移除 <UUID>` | `/restrictforceremove <uuid>` | 強制移除指定 UUID 的所有資料 | OP |

## 設定

- 請先建立 LuckPerms 群組，例如 `lp creategroup frozen`，並依需求設定該群組的（否定）權限。
- 登入提示訊息可依伺服器規則修改（最後一行提到群眾投票）。

## 注意事項

- 資料存放在 `{freeze.*}` 變數，兩個版本共用。
- 以名稱查詢離線玩家時會逐一比對所有曾登入的玩家，大型伺服器建議改用 UUID 指令。

## 相關專案

- [skript-contraband-item-scanner](https://github.com/Im-Tim-mI/skript-contraband-item-scanner)－違禁方塊檢測系統

## 授權

**MIT + Commons Clause**，完整條款請見 [LICENSE](LICENSE)。

- ✅ 可自由使用、複製、修改與分享本腳本。
- ✅ 本授權明確允許在收費或營利的 Minecraft 伺服器上安裝與運行本插件（含修改版）。
- ❌ 禁止的僅限於直接或間接販售本插件本體、修改版本，或以付費方式取得其檔案或原始碼。

Copyright (c) 2026 廷廷小教室、廷廷的家（Tim945）
