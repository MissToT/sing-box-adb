# sing-box 广告规则集

自动将 [10007 大佬的广告规则](https://github.com/lingeringsound/10007)、[anti-AD](https://github.com/privacy-protection-tools/anti-AD) 以及 [Adblock-Rule-Collection](https://github.com/REIJI007/Adblock-Rule-Collection) 转换为 sing-box `rule-set` 格式，每天自动更新。

## 下载

- **adb.srs**（Adguard 规则）

| 名称 | 链接 | Github 加速链接 |
|------|------|----------------|
| sing-box 规则集 | [订阅链接](https://raw.githubusercontent.com/MissToT/sing-box-adb/main/adb.srs) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/MissToT/sing-box-adb/raw/refs/heads/main/adb.srs) |
| Adguard 规则 | [订阅链接](https://raw.githubusercontent.com/lingeringsound/10007/main/adb.txt) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/lingeringsound/10007/raw/refs/heads/main/adb.txt) |

- **all.srs**（完整规则）

| 名称 | 链接 | Github 加速链接 |
|------|------|----------------|
| sing-box 规则集 | [订阅链接](https://raw.githubusercontent.com/MissToT/sing-box-adb/main/all.srs) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/MissToT/sing-box-adb/raw/refs/heads/main/all.srs) |
| Adguard 规则 | [订阅链接](https://raw.githubusercontent.com/lingeringsound/10007/main/all) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/lingeringsound/10007/raw/refs/heads/main/all) |

- **reward.srs**（保留广告奖励）

| 名称 | 链接 | Github 加速链接 |
|------|------|----------------|
| sing-box 规则集 | [订阅链接](https://raw.githubusercontent.com/MissToT/sing-box-adb/main/reward.srs) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/MissToT/sing-box-adb/raw/refs/heads/main/reward.srs) |
| Adguard 规则 | [订阅链接](https://raw.githubusercontent.com/lingeringsound/10007/main/reward) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/lingeringsound/10007/raw/refs/heads/main/reward) |

- **anti-ad-adguard.srs**（anti-AD · AdGuard 格式，匹配整个URL的域名部分）

| 名称 | 链接 | Github 加速链接 |
|------|------|----------------|
| sing-box 规则集 | [订阅链接](https://raw.githubusercontent.com/MissToT/sing-box-adb/main/anti-ad-adguard.srs) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/MissToT/sing-box-adb/raw/refs/heads/main/anti-ad-adguard.srs) |
| Adguard 规则 | [订阅链接](https://raw.githubusercontent.com/privacy-protection-tools/anti-AD/master/anti-ad-adguard.txt) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/privacy-protection-tools/anti-AD/raw/refs/heads/master/anti-ad-adguard.txt) |

- **anti-ad-easylist.srs**（anti-AD · EasyList 格式，AdGuard Home DNS过滤）

| 名称 | 链接 | Github 加速链接 |
|------|------|----------------|
| sing-box 规则集 | [订阅链接](https://raw.githubusercontent.com/MissToT/sing-box-adb/main/anti-ad-easylist.srs) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/MissToT/sing-box-adb/raw/refs/heads/main/anti-ad-easylist.srs) |
| EasyList 规则 | [订阅链接](https://raw.githubusercontent.com/privacy-protection-tools/anti-AD/master/anti-ad-easylist.txt) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/privacy-protection-tools/anti-AD/raw/refs/heads/master/anti-ad-easylist.txt) |

- **adblock-rule-collection.srs**（Adblock-Rule-Collection · 多源聚合规则）

| 名称 | 链接 | Github 加速链接 |
|------|------|----------------|
| sing-box 规则集 | [订阅链接](https://raw.githubusercontent.com/MissToT/sing-box-adb/main/adblock-rule-collection.srs) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/MissToT/sing-box-adb/raw/refs/heads/main/adblock-rule-collection.srs) |
| Adguard 规则 | [订阅链接](https://raw.githubusercontent.com/REIJI007/Adblock-Rule-Collection/main/ADBLOCK_RULE_COLLECTION.txt) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/REIJI007/Adblock-Rule-Collection/raw/refs/heads/main/ADBLOCK_RULE_COLLECTION.txt) |

## 在 sing-box 中使用

在你的 `config.json` 中添加（以 `adb.srs` 为例）：

```json
{
  "route": {
    "rule_set": [
      {
        "tag": "adb",
        "type": "remote",
        "format": "binary",
        "update_interval": "24h",
        "path": "./rules/adb.srs",
        "url": "https://raw.githubusercontent.com/MissToT/sing-box-adb/main/adb.srs",
      }
    ],
    "rules": [
      {
        "rule_set": "adb",
        "action": "reject",
        "method": "drop"
      }
    ]
  }
}
```

## 规则来源

- 上游规则（10007）：[lingeringsound/10007](https://github.com/lingeringsound/10007)
- 上游规则（anti-AD）：[privacy-protection-tools/anti-AD](https://github.com/privacy-protection-tools/anti-AD)
- 上游规则（Adblock-Rule-Collection）：[REIJI007/Adblock-Rule-Collection](https://github.com/REIJI007/Adblock-Rule-Collection)
- 转换工具：[SagerNet/sing-box](https://github.com/SagerNet/sing-box)

## 更新频率

每天北京时间 **06:00** 自动拉取上游最新规则并重新转换。

若规则无变化则跳过提交，节省仓库空间。

---

> 本仓库由 GitHub Actions 自动维护，无需手动操作。
