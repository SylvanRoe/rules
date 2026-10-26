# 自定义分流规则集 (Rules)

个人网络代理与分流规则集合，支持 Surge、Clash、Shadowrocket、Loon、Quantumult X、Stash 等客户端。

## 规则集列表

| 规则集名称 | 文件名 | 说明 | 订阅链接 (Raw) |
| :--- | :--- | :--- | :--- |
| **Apple / Siri** | `Apple.list` | Apple Intelligence、Siri、PCC 云计算及 Private Relay 代理规则 | [点击获取](https://raw.githubusercontent.com/SylvanRoe/rules/main/Apple.list) |
| **Emby (规划中)** | `Emby.list` | 媒体播放与 Emby 服务器分流规则 | *(后续更新)* |

---

## Apple 规则订阅与引用地址

- **GitHub Raw 原生地址**:
  `https://raw.githubusercontent.com/SylvanRoe/rules/main/Apple.list`
- **国内加速镜像 (jsDelivr CDN)**:
  `https://fastly.jsdelivr.net/gh/SylvanRoe/rules@main/Apple.list`

### Surge 配置示例
```ini
[Rule]
RULE-SET,https://raw.githubusercontent.com/SylvanRoe/rules/main/Apple.list,PROXY
```

### Clash / Stash 配置示例
```yaml
rule-providers:
  AppleRules:
    type: http
    behavior: classical
    url: "https://raw.githubusercontent.com/SylvanRoe/rules/main/Apple.list"
    path: ./ruleset/Apple.yaml
    interval: 86400

rules:
  - RULE-SET,AppleRules,PROXY
```
