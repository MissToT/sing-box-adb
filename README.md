# sing-box 广告规则集

自动将 [10007 大佬的广告规则](https://github.com/lingeringsound/10007) 转换为 sing-box `rule-set` 格式，每天自动更新。

## 下载

| 名称 | 链接 | Github 加速链接 |
|------|------|----------------|
| sing-box 广告规则集 | [订阅链接](https://raw.githubusercontent.com/MissToT/sing-box-adb/main/adb.srs) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/MissToT/sing-box-adb/raw/refs/heads/main/adb.srs) |
| Adguard 规则 | [订阅链接](https://raw.githubusercontent.com/lingeringsound/10007/main/adb.txt) | [Github 加速订阅链接](https://v6.gh-proxy.org/github.com/lingeringsound/10007/raw/refs/heads/main/adb.txt) |

## 在 sing-box 中使用

在你的 `config.json` 中添加：

```json
{
  "route": {
    "rule_set": [
      {
        "tag": "adb",
        "type": "remote",
        "format": "binary",
        "url": "https://raw.githubusercontent.com/MissToT/sing-box-adb/main/adb.srs",
        "download_detour": "direct"
      }
    ],
    "rules": [
      {
        "rule_set": "adb",
        "outbound": "block"
      }
    ]
  }
}
```

## 规则来源

- 上游规则：[lingeringsound/10007](https://github.com/lingeringsound/10007)
- 转换工具：[SagerNet/sing-box](https://github.com/SagerNet/sing-box)

## 更新频率

每天北京时间 **06:00** 自动拉取上游最新规则并重新转换。

若规则无变化则跳过提交，节省仓库空间。

---

> 本仓库由 GitHub Actions 自动维护，无需手动操作。
