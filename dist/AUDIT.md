# Proxy-Rules-Factory 自动构建审计报告

- **构建时间**：`2026-11-24 07:23:45 UTC`
- **上游原始规则总量**：`12127` 条
- **清洗后输出规则总量**：`10099` 条（零重复、零冲突、零死规则、零超限截断）
- **自动清理统计**：组内冗余 `748` 条 ｜ 跨组精确冲突 `1254` 条 ｜ 跨组父域遮蔽 `26` 条

## 各业务分组产出明细（按优先级从高到低）

| 优先级 | 策略组 | 文件 | 输出规则数 | 体积 | 组内去重 | 跨组冲突清理 | 父域遮蔽清理 |
|---:|---|---|---:|---:|---:|---:|---:|
| 1 | 🏠 局域服务 | `dist/rules/lan.list` | 153 | 4.9 KB | 126 | 0 | 0 |
| 2 | 🤓 私人服务 | `dist/rules/private_direct.list` | 15 | 0.6 KB | 0 | 0 | 0 |
| 3 | 🚁 动态直连 | `dist/rules/dynamic_direct.list` | 3 | 0.2 KB | 0 | 0 | 0 |
| 4 | 🚻 动态代理 | `dist/rules/dynamic_proxy.list` | 3 | 0.2 KB | 0 | 0 | 0 |
| 5 | ☎️ 国外-DNS | `dist/rules/foreign_dns.list` | 30 | 1.0 KB | 0 | 0 | 0 |
| 6 | ⬆️ 苹果升级 | `dist/rules/apple_ota.list` | 78 | 2.8 KB | 0 | 0 | 0 |
| 7 | 🤖 OpenAI | `dist/rules/ai_openai.list` | 24 | 0.9 KB | 0 | 0 | 0 |
| 8 | 🤖 Gemini | `dist/rules/ai_gemini.list` | 50 | 1.9 KB | 0 | 0 | 0 |
| 9 | 🤖 Claude & AI | `dist/rules/ai_other.list` | 145 | 4.2 KB | 36 | 74 | 0 |
| 10 | 🤖 微软助手 | `dist/rules/ai_copilot.list` | 31 | 1.1 KB | 10 | 4 | 0 |
| 11 | 📱 GV号服务 | `dist/rules/google_voice.list` | 4 | 0.3 KB | 0 | 0 | 0 |
| 12 | 📹 油管视频 | `dist/rules/youtube.list` | 177 | 4.9 KB | 1 | 0 | 0 |
| 13 | 🎥 奈飞视频 | `dist/rules/netflix.list` | 146 | 5.4 KB | 0 | 0 | 0 |
| 14 | 🎵 海外抖音 | `dist/rules/tiktok.list` | 39 | 1.3 KB | 1 | 0 | 0 |
| 15 | 🐉 巴哈姆特 | `dist/rules/bahamut.list` | 5 | 0.3 KB | 0 | 0 | 0 |
| 16 | 📳 电报代理 | `dist/rules/telegram.list` | 33 | 1.1 KB | 0 | 0 | 0 |
| 17 | 🕊️ 推特代理 | `dist/rules/twitter.list` | 24 | 0.8 KB | 0 | 0 | 0 |
| 18 | 🪙 加密货币 | `dist/rules/crypto.list` | 241 | 6.6 KB | 0 | 0 | 0 |
| 19 | 🐙 GitHub | `dist/rules/github.list` | 57 | 2.3 KB | 2 | 7 | 0 |
| 20 | 🔎 谷歌服务 | `dist/rules/google.list` | 687 | 18.6 KB | 201 | 191 | 0 |
| 21 | 🍎 苹果直连 | `dist/rules/apple_cn.list` | 151 | 4.9 KB | 2 | 10 | 4 |
| 22 | 🍎 苹果服务 | `dist/rules/apple.list` | 1420 | 44.4 KB | 90 | 157 | 1 |
| 23 | Ⓜ️ 微软直连 | `dist/rules/microsoft_cn.list` | 185 | 6.2 KB | 0 | 2 | 6 |
| 24 | Ⓜ️ 微软服务 | `dist/rules/microsoft.list` | 438 | 13.1 KB | 42 | 279 | 0 |
| 25 | 📺 国内媒体 | `dist/rules/cn_media.list` | 1509 | 41.5 KB | 212 | 46 | 0 |
| 26 | 📶 网络测速 | `dist/rules/speedtest.list` | 20 | 0.7 KB | 0 | 0 | 0 |
| 27 | 📥 下载服务 | `dist/rules/download_pt.list` | 429 | 10.9 KB | 6 | 0 | 2 |
| 28 | 🧱 防火长城 | `dist/rules/gfw.list` | 3966 | 106.8 KB | 0 | 483 | 13 |
| 29 | 🎮 国内游戏 | `dist/rules/cn_games.list` | 36 | 1.3 KB | 19 | 1 | 0 |

## 跨组父域遮蔽自动清理样本（前 25 条）

- `DOMAIN,appldnld.apple.com` (🍎 苹果直连) 已被更高优先级父域 `appldnld.apple.com` (⬆️ 苹果升级) 覆盖，已自动剔除死规则
- `DOMAIN,appldnld.g.aaplimg.com` (🍎 苹果直连) 已被更高优先级父域 `appldnld.g.aaplimg.com` (⬆️ 苹果升级) 覆盖，已自动剔除死规则
- `DOMAIN,mesu-cdn.apple.com.akadns.net` (🍎 苹果直连) 已被更高优先级父域 `mesu-cdn.apple.com.akadns.net` (⬆️ 苹果升级) 覆盖，已自动剔除死规则
- `DOMAIN,mesu.apple.com` (🍎 苹果直连) 已被更高优先级父域 `mesu.apple.com` (⬆️ 苹果升级) 覆盖，已自动剔除死规则
- `DOMAIN,mesu-cdn.apple.com.akadns.net` (🍎 苹果服务) 已被更高优先级父域 `mesu-cdn.apple.com.akadns.net` (⬆️ 苹果升级) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,cn.bing.com` (Ⓜ️ 微软直连) 已被更高优先级父域 `bing.com` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,cn.bing.net` (Ⓜ️ 微软直连) 已被更高优先级父域 `bing.net` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,cn.mm.bing.net` (Ⓜ️ 微软直连) 已被更高优先级父域 `bing.net` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,r.bing.com` (Ⓜ️ 微软直连) 已被更高优先级父域 `bing.com` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,th.bing.com` (Ⓜ️ 微软直连) 已被更高优先级父域 `bing.com` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN,bj1.api.bing.com` (Ⓜ️ 微软直连) 已被更高优先级父域 `bing.com` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN,academic-p2p.appspot.com` (📥 下载服务) 已被更高优先级父域 `appspot.com` (🔎 谷歌服务) 覆盖，已自动剔除死规则
- `DOMAIN,carbon-bonsai-621.appspot.com` (📥 下载服务) 已被更高优先级父域 `appspot.com` (🔎 谷歌服务) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,sydney.bing.com` (🧱 防火长城) 已被更高优先级父域 `bing.com` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,updates.tdesktop.com` (🧱 防火长城) 已被更高优先级父域 `tdesktop.com` (📳 电报代理) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,onedrive.live.com` (🧱 防火长城) 已被更高优先级父域 `live.com` (Ⓜ️ 微软服务) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,issues.chromium.org` (🧱 防火长城) 已被更高优先级父域 `chromium.org` (🔎 谷歌服务) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,global.bing.com` (🧱 防火长城) 已被更高优先级父域 `bing.com` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,files.oaiusercontent.com` (🧱 防火长城) 已被更高优先级父域 `oaiusercontent.com` (🤖 OpenAI) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,www.bing.com` (🧱 防火长城) 已被更高优先级父域 `bing.com` (🤖 微软助手) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,www.msn.com` (🧱 防火长城) 已被更高优先级父域 `msn.com` (Ⓜ️ 微软服务) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,www.skype.com` (🧱 防火长城) 已被更高优先级父域 `skype.com` (Ⓜ️ 微软服务) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,console.typesafe.ai` (🧱 防火长城) 已被更高优先级父域 `typesafe.ai` (🤖 Claude & AI) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,cloud.dify.ai` (🧱 防火长城) 已被更高优先级父域 `dify.ai` (🤖 Claude & AI) 覆盖，已自动剔除死规则
- `DOMAIN-SUFFIX,backend-v2.crixet.com` (🧱 防火长城) 已被更高优先级父域 `crixet.com` (🤖 OpenAI) 覆盖，已自动剔除死规则
