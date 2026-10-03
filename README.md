# Player Restriction

**English** | [繁體中文](README.zh-TW.md)

A “freeze” moderation tool: restricted players can still join and chat, but can't build, break, interact, fight, open containers, ride, sleep or run commands. Works by name or UUID, so Bedrock players with a `.` prefix are supported.

> This repository has two editions of the same script: **繁體中文 (zh-TW)** is the original used on the author's Traditional Chinese server, and **English** is a full translation (commands, messages and variable names) with the same features.

## Features

- Restrict by player name (online or offline) or by UUID, with a reason, executor and time
- Server-wide broadcasts when a player is restricted or released, and when a restricted player joins
- Blocks placing / breaking blocks, clicking, attacking, dropping, picking up, opening containers, shooting, riding, beds, trampling farmland and every command
- Also adds the player to the LuckPerms group `frozen`
- Status, list, cleanup and force-remove tools for admins

## Requirements

- [Paper](https://papermc.io/) server (developed on Paper 26.2 / Minecraft 26.2)
- [Skript](https://github.com/SkriptLang/Skript) (developed on 2.16.2)
- [skript-reflect](https://github.com/SkriptLang/skript-reflect) (developed on 2.6.3) (farmland protection)
- [LuckPerms](https://luckperms.net/) (group `frozen`)

## Installation

1. Install the plugins listed under [Requirements](#requirements).
2. Download **one** edition:

   | Edition | File(s) |
   |---|---|
   | English | [`en/player-restriction.sk`](en/player-restriction.sk) |
   | 繁體中文 (original) | [`zh-TW/玩家限制系統.sk`](zh-TW/%E7%8E%A9%E5%AE%B6%E9%99%90%E5%88%B6%E7%B3%BB%E7%B5%B1.sk) |

3. Copy the `.sk` file(s) into `plugins/Skript/scripts/` on your server.
4. Run `/sk reload player-restriction` (use the file name you copied) or restart the server.

> [!IMPORTANT]
> Install **only one** edition. Both editions are the same script in different languages - loading both makes them clash or run twice.

## Commands

| Command (English edition) | zh-TW edition | Description | Permission |
|---|---|---|---|
| `/restrict <player> <reason>` | `/限制 <玩家名稱> <限制原因>` | Restrict a player | OP |
| `/restrictuuid <uuid> <reason>` | `/限制uuid <UUID> <限制原因>` | Restrict by UUID | OP |
| `/unrestrict <player>` | `/解除限制 <玩家名稱>` | Lift a restriction | OP |
| `/unrestrictuuid <uuid>` | `/解除限制uuid <UUID>` | Lift a restriction by UUID | OP |
| `/restrictstatus <player or uuid>` | `/限制狀態 <玩家名稱或UUID>` | Show restriction details | OP |
| `/restrictlist` | `/限制列表` | List restricted players | OP |
| `/restrictcleanup` | `/限制清理` | Remove duplicate / invalid entries | OP |
| `/restrictforceremove <uuid>` | `/強制移除 <UUID>` | Force-remove a UUID from all data | OP |

## Configuration

- Create the LuckPerms group first, e.g. `lp creategroup frozen`, and give it whatever (negated) permissions you like.
- Adapt the join message to your server's rules (the last line mentions a community vote).

## Notes

- Data is stored in `{freeze.*}` variables, the same in both editions.
- Looking up offline players by name loops over every player who has ever joined; on big servers the UUID commands are faster.

## Related projects

- [skript-contraband-item-scanner](https://github.com/Im-Tim-mI/skript-contraband-item-scanner) - Contraband Item Scanner

## License

**MIT + Commons Clause** - see [LICENSE](LICENSE) for the full text.

- ✅ You may use, copy, modify and share this script.
- ✅ You **may** install and run it - including modified versions - on Minecraft servers that charge money or are run for profit.
- ❌ You may **not** sell the script itself or modified versions of it, directly or indirectly, or require payment to obtain its files or source code.

Copyright (c) 2026 廷廷小教室、廷廷的家（Tim945）
