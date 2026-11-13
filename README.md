# Minecraft-1.21.11-Paper-Skript.Plugin

SCL 服务器正在使用 / 准备上线使用的 Skript 插件合集，基于 Paper 1.21.11 + Skript 2.11 编写，MIT 协议开源。

## 介绍

这个仓库放的是 SCL 服务器实际在跑的服务端脚本，不是示范工程——每个 `.sk` 文件对应一个完整功能模块，拖进 `plugins/Skript/scripts/` 就能用，不需要编译、不需要额外的前置插件开发。

目前包含两个模块：

- **经验银行（`expbank.sk`）**：把原版经验变成可存取的"账户"。玩家可以把身上的经验点存入银行、按需取出、玩家之间互相转账、随时查余额；管理员用 `set/add/remove/reset` 直接改账。数据按 UUID 记账，另带 `/eb`、`/bank` 两个别名和一页 GUI 菜单。
- **原版统计排行榜（`LB-leaderboards.sk`）**：挖掘、建造、死亡、击杀、钓鱼、在线时长六类全服排行。它不自己记数，而是读取 Minecraft 原版统计数据，所以**装脚本之前的历史记录同样计入**；榜单定期扫描后写进 YAML 缓存，命令和占位符读缓存，不会给服务器添负担。

两个脚本都暴露了 PAPI 占位符（`%expbank_balance%`、`%lb_top_mined_1_name%` 等），可以直接接进 TAB、计分板或聊天格式里。

## 插件列表

| 名称 | 状态 | 功能 | 说明 |
|------|------|------|------|
|经验银行系统（ExpBank） expbank.sk | ✅ | 允许玩家把经验点存入「银行」、按需取出、互相转账、查余额，并提供管理员操作与 GUI 菜单 | 见下方依赖 |
|原版统计排行榜 LB-leaderboards.sk | 未经验证 | 多类型全服排行榜脚本：挖掘、建造、死亡、击杀、钓鱼、在线时长，一条命令查看上榜 | 见下方依赖 |

## 依赖

| 插件 | 用途 |
|---|---|
| Skript **2.11+** | 核心 |
| skript-placeholders | 注册 / 读取 PAPI 占位符 |
| skript-yaml | 排行榜数据持久化（仅 `LB-leaderboards.sk`） |
| PlaceholderAPI + **Statistics-Expansion** | 原版统计数据的来源（仅 `LB-leaderboards.sk`） |
| DeluxeMenus | 经验银行的 `/bank` 菜单（需自备 `expbank` 菜单配置） |

## 安装

1. 装好上表插件，`/papi ecloud download statistic` 确认统计扩展已安装
2. 把需要的 `.sk` 文件放进 `plugins/Skript/scripts/`
3. `/sk reload expbank` 或 `/sk reload LB-leaderboards`
4. 排行榜需先执行 `/lbrescan` 建立数据；老玩家用 `/lbadd <玩家名>` 补录

## 说明 / 注意事项

**经验银行**

- 余额用 Skript 变量按 UUID 存储，属于内存变量，Skript 重启后清空；如需长期保留请自行接 skript-yaml。
- `/bank` 菜单走的是 `dm open expbank`，需要 DeluxeMenus 中已存在名为 `expbank` 的菜单。
- 转账要求对方在线，且不能转给自己；单笔最小金额由脚本顶部 `min_amount` 控制。

**排行榜**

- 原版统计只按玩家存，没有"全服玩家列表"，脚本维护一份 `known` 名单；装脚本前的老玩家需 `/lbadd` 或上线一次才会进榜。
- `statistic_mine_block` 开销较大，扫描间隔为 15 分钟；请勿在秒级刷新的计分板里直接读它，读 `%lb_*%` 缓存即可。
- 若 `%statistic_place_block%` 返回空值，建造榜可能为空表，可换成 `statistic_jump` 等纯数值统计。

## 参与贡献

欢迎通过 [Issues](https://github.com/SCL-100/Minecraft-1.21.11-Paper-Skript.Plugin/issues) 或 Pull Request 参与共建。

## 许可

[MIT License](LICENSE) © 2026 SCL-100
