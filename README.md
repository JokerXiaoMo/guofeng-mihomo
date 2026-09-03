<div align="center">

# 云隐阁 · 国风 mihomo

**国风二次元定制版 mihomo 配置覆写脚本**

*一纸覆写，千机入阁。*

[![内核](https://img.shields.io/badge/内核-mihomo%20%2F%20Clash%20Meta-8A2BE2?style=flat-square)](https://github.com/MetaCubeX/mihomo)
[![类型](https://img.shields.io/badge/类型-覆写脚本%20Script-CC6699?style=flat-square)](#-使用方法)
[![风格](https://img.shields.io/badge/风格-国风%20%2F%20二次元-D4A017?style=flat-square)](#-策略组雅号对照)
[![License](https://img.shields.io/badge/协议-MIT-3DA639?style=flat-square)](#-开源协议)

</div>

---

## 📖 简介

**「云隐阁」** 是一份面向 [mihomo](https://github.com/MetaCubeX/mihomo)（Clash Meta）内核的**配置覆写脚本**：将机场订阅覆写为一套国风雅号命名的完整策略组体系，并针对「**超稳定、超低延迟访问各个 APP**」做了四项增强。

> 🙏 **本项目基于 [AIsouler/MyClash](https://github.com/AIsouler/MyClash) 的 `mihomoScript.js` 微改而来**——分流逻辑、规则集与节点处理均出自原作者之手，在此致以诚挚谢意。本版在其基础上做了**国风二次元化命名**与**连接稳定性增强**，并重新设计了文档与项目结构。

---

## 🌟 四项增强（面向超稳定、超低延迟）

| # | 增强 | 效果 |
| :-: | :--- | :--- |
| 1 | **sniffer 域名嗅探** | TLS/HTTP 域名嗅探，分流更精准；QUIC 被拦截时自动回落 TCP，视频 / 语音不断流 |
| 2 | **`global-client-fingerprint: chrome`** | 统一 TLS 指纹，降低 CDN 风控拦截概率，连接更稳 |
| 3 | **`keep-alive-interval` 30s + `tcp-keep-alive-idle` 30s** | 空闲保活，NAT 映射不易失效，减少重连与延迟抖动 |
| 4 | **「御风」自动组 · 50ms 容差 url-test** | 实时测速、始终自动切换最低延迟线路 |

此外完整继承了原脚本的招牌能力：

- 🔄 根据节点名称**动态生成地区策略组**（自动补全国旗、剔除信息节点）
- ⚖️ 自动识别**低倍率 / 高倍率**节点并归类
- 🩹 自动解决机场**私有 DNS / hosts 映射**导致的节点域名解析问题（hosts 改写进节点 server），DNS 无泄露
- 🧩 支持**自定义节点**（自动生成「本命·自建」组）与**链式代理**（自定义节点作落地、经「合道·中转」中转）
- 🚫 可选屏蔽国外 QUIC、过滤高倍率 / 非地区节点、IPv4 / IPv6 优先

---

## 🏮 策略组雅号对照

**基础策略组**

| 原名 | 云隐阁雅号 | | 原名 | 云隐阁雅号 |
| :--- | :--- | :-: | :--- | :--- |
| 手动选择 | 「执印」手动 | | 默认代理 | 「太一」主道 |
| 自动选择 | 「御风」自动 | | 直连 | 「凡尘」直连 |
| 负载均衡 | 「混元」均衡 | | 漏网之鱼 | 「补天」兜底 |

**地区与倍率**

| 原名 | 雅号 | | 原名 | 雅号 |
| :--- | :--- | :-: | :--- | :--- |
| 中国香港 | 香江 🇭🇰 | | 低倍率节点 | 轻羽·低倍 |
| 中国澳门 | 濠镜 🇲🇴 | | 高倍率节点 | 重岳·高倍 |
| 日本 | 东瀛 🇯🇵 | | 其他节点 | 散修·散点 |
| 美国 | 花旗 🇺🇸 | | 自建节点 | 本命·自建 |
| 新加坡 | 狮城 🇸🇬 | | 链式中转 / 落地 | 合道·中转 / 合道·落地 |
| 中国台湾 | 宝岛 🇨🇳 | | | |

**分流策略组**

| 服务 | 雅号 | | 服务 | 雅号 |
| :--- | :--- | :-: | :--- | :--- |
| Google FCM | 灵鸽·传讯 | | Telegram | 飞书·电报 |
| YouTube | 映画·油管 | | Steam | 雾阁·蒸汽 |
| Google | 星图·谷歌 | | TikTok | 幻音·短影 |
| 国外 AI | 天工·灵智 | | Twitter | 栖鸾·推特 |
| Microsoft | 云笈·微软 | | Instagram | 绘镜·影格 |
| Apple | 玉果·苹果 | | Netflix | 映雪·奈飞 |
| Emby | 藏经阁·影库 | | PikPak | 行囊·网盘 |
| Spotify | 韶音·声乐 | | 加密货币 | 通宝·加密 |
| E-Hentai | 秘阁·E站 | | 广告拦截 | 结界·拦截 |

---

## 🚀 使用方法

### 一键 Raw 直链（推荐，方便后续同步更新）

脚本直链，可直接在支持「链接覆写 / 远程脚本」的客户端中填入：

```
https://raw.githubusercontent.com/JokerXiaoMo/guofeng-mihomo/main/Script/guofeng-mihomo.js
```

> 若 `raw.githubusercontent.com` 无法直连，可改用加速前缀：
> ```
> https://fastly.jsdelivr.net/gh/JokerXiaoMo/guofeng-mihomo@main/Script/guofeng-mihomo.js
> ```

### Clash Verge Rev（覆写方式）

1. 订阅列表 → 右键你的机场订阅 → **编辑脚本**（或 全局扩展配置 → Script）
2. 粘贴 [`Script/guofeng-mihomo.js`](Script/guofeng-mihomo.js) 全文保存
3. **关闭客户端自带的 DNS 覆写**（设置 → DNS 覆写关闭），交给脚本接管
4. 重新激活订阅，即可看到全套国风策略组

### Mihomo Party / 其他 Script 覆写客户端

同上：在「覆写 / Override → JavaScript」中粘贴脚本全文，保存并启用即可。

### Bettbox（原生适配）

脚本内置 `Compatible_With_Bettbox`，Bettbox 可直接识别脚本中的自定义配置选项，图形化开关各项功能。

### ⚠️ 注意事项

- 仅用于**机场提供的订阅配置文件**进行覆写，勿用于自行编写的配置
- 需**关闭代理软件自带的 DNS 覆写功能**，避免与脚本生成的 DNS 配置冲突
- 想修改开关 / 添加自定义节点？直接编辑脚本顶部「静态配置区域」，注释齐全

---

## 🎛 自定义开关速览

脚本顶部的 `ruleOptionsEnable` 提供全部开关（`true` 启用 / `false` 禁用），常用项：

| 开关 | 说明 |
| :--- | :--- |
| `生成地区自动选择组` | 每个地区附带一个 `·御风` url-test 自动组 |
| `隐藏地区手动选择组` | 面板中隐藏地区手动选择组，只留自动组 |
| `生成倍率组` | 生成「轻羽·低倍 / 重岳·高倍」分组 |
| `过滤高倍率节点` / `过滤非地区节点` | 节点过滤 |
| `屏蔽国外QUIC` | 屏蔽国外 UDP 443（QUIC），配合 sniffer 自动回落 TCP |
| `代理IPV4优先` / `代理IPV6优先` | 节点 IP 栈偏好（二者只开一个） |
| `链式代理` | 自定义节点作为落地，经「合道·中转」中转 |
| 各分流组（`映画·油管` 等） | 关闭后该策略组与对应规则整体移除 |

---

## 📁 目录结构

```
guofeng-mihomo
├── Script/
│   └── guofeng-mihomo.js   # 覆写脚本本体
├── README.md
└── LICENSE
```

---

## 🙏 致谢

本项目得以成立，离不开以下项目与作者（**排名分先后，诚意不分先后**）：

- **[AIsouler/MyClash](https://github.com/AIsouler/MyClash)** —— ⭐ **原脚本作者**。本项目的覆写脚本基于其 `mihomoScript.js` 微改而来：节点过滤与地区归组、机场私有 DNS / hosts 修复、倍率识别、链式代理等核心能力均出自原作者之手，云隐阁不过是在巨人的肩上描了一层国风的漆。**强烈建议去给原项目点一个 Star。**
- [MetaCubeX/mihomo](https://github.com/MetaCubeX/mihomo) —— 强大的代理内核
- [appshubcc/bett-rules](https://github.com/appshubcc/bett-rules) —— 规则集来源
- [appshubcc/Bettbox](https://github.com/appshubcc/Bettbox) —— 好用、省电且内存占用低的代理软件（友情推荐）
- [Koolson/Qure](https://github.com/Koolson/Qure) —— 策略组图标
- [217heidai/AdBlockFilters](https://github.com/217heidai/AdBlockFilters) —— 广告过滤规则
- [wwqgtxx/clash-rules](https://github.com/wwqgtxx/clash-rules)、[666OS/rules](https://github.com/666OS/rules)、[binaryu/emos-proxy-rule](https://github.com/binaryu/emos-proxy-rule) —— 补充规则
- [Zephyruso/zashboard](https://github.com/Zephyruso/zashboard) —— 控制面板

---

## ⚠️ 免责声明

本项目仅供学习与研究网络技术使用，不提供任何节点 / 订阅，也不承载任何流量。请遵守所在地区的法律法规，合理使用代理工具。

## 📜 开源协议

本项目文档与项目结构以 [MIT](LICENSE) 协议开源。

覆写脚本 `Script/guofeng-mihomo.js` 为 [AIsouler/MyClash](https://github.com/AIsouler/MyClash)（未附带开源协议）之 `mihomoScript.js` 的修改版本，其著作权归属原作者 AIsouler；本项目在使用处均已显著标注来源。若原作者提出异议，将第一时间处理。

---

<div align="center">

**若云隐阁为你遮过一阵风雨，欢迎点一个 ⭐ Star，也请记得给 [AIsouler/MyClash](https://github.com/AIsouler/MyClash) 点一个**

*阁中一盏灯，照夜行之人。*

</div>
