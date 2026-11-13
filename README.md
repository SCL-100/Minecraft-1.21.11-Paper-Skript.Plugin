# Minecraft-1.21.11-Paper-Skript.Plugin

SCL 服务器正在使用 / 准备上线使用的 Skript 插件合集，基于 Paper 1.21.11 + Skript 2.11 编写，遵循 MIT 协议开源。

## 插件列表

| 名称 | 状态 | 功能 | 说明 |
|------|------|------|------|
|经验银行系统（ExpBank） expbank.sk | ✅ | 允许玩家把经验点存入「银行」、按需取出、互相转账、查余额，并提供管理员操作与 GUI 菜单 | 见下方依赖 |
|原版统计排行榜 LB-leaderboards.sk | 未经验证 | 多类型全服排行榜脚本：挖掘、建造、死亡、击杀、钓鱼、在线时长，一条命令查看上榜 | 见下方依赖 |
|陶罐酿酒系统（Brewery） brewery.sk | ✅ | 右键陶罐投入原料开始酿造，玻璃瓶取出成品；16 种酒 + 1 种假酒，陶罐下垫营火进入蒸馏模式（时间翻倍、酒劲更烈）。饮酒获得药水效果并累积醉酒度，分清醒 / 微醺 / 酩酊大醉 / 烂醉如泥四档，高醉会掉血、反胃、踉跄，喝牛奶可解酒 | 需 Skript 2.14+，无其他插件依赖 |
|低保系统（Dibao） dibao.sk | 🐛 已知 BUG | 金币低于阈值（默认 20）的玩家可申请每日金币补助，管理员审核通过后连续 5 天自动发放，每天 160 金币；含 status 查询、admin 审核列表、add 手动添加、test 手动测试 | 见 [Issue #1](https://github.com/SCL-100/Minecraft-1.21.11-Paper-Skript.Plugin/issues/1)；需 Vault + 经济插件 |

## 依赖

| 插件 |
|---|
| Skript **2.14+** | 
| skript-placeholders | 
| skript-yaml | 
| PlaceholderAPI + **Statistics-Expansion** |
| DeluxeMenus |
| Vault + 经济插件 |

欢迎通过 [Issues](https://github.com/SCL-100/Minecraft-1.21.11-Paper-Skript.Plugin/issues) 或 Pull Request 参与共建。

## 许可

[MIT License](LICENSE) © 2026 SCL-100
