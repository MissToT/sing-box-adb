# sing-box 广告规则集

自动将 [10007 大佬的广告规则](https://github.com/lingeringsound/10007) 转换为 sing-box `rule-set` 格式，每天自动更新。

## 文件说明

| 文件 | 说明 |
|------|------|
| `adb.srs` | sing-box 二进制规则集（直接使用） |
| `adb.txt` | 原始 AdGuard 规则（来自 10007） |
| `metadata.json` | 更新时间及统计信息 |

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
        "url": "https://raw.githubusercontent.com/<你的用户名>/<仓库名>/main/adb.srs",
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
