# Minecraft-1.21.11-Paper-Skript.Plugin

SCL 服务器正在使用 / 准备上线使用的 Skript 插件合集，基于 Paper 1.21.11 + Skript 2.11 编写，遵循 MIT 协议开源。

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

欢迎通过 [Issues](https://github.com/SCL-100/Minecraft-1.21.11-Paper-Skript.Plugin/issues) 或 Pull Request 参与共建。

## 许可

[MIT License](LICENSE) © 2026 SCL-100
