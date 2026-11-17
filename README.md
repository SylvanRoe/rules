# 自定义分流规则集 (Rules)

个人网络代理与分流规则集合，支持 Surge、Clash、Shadowrocket、Loon、Quantumult X、Stash 等客户端。

## 规则集列表

| 规则集名称 | 文件名 | 说明 | 订阅链接 (Raw) |
| :--- | :--- | :--- | :--- |
| **Apple / Siri** | `Apple.list` | Apple Intelligence、Siri、PCC 云计算及 Private Relay 代理规则 | [点击获取](https://raw.githubusercontent.com/SylvanRoe/rules/main/Apple.list) |
| **CK 凭证获取合集** | `CK.conf` | 25 个 CK（Cookie 获取）重写来源合并为一个文件，QX 引用后按需开启 | [点击获取](https://raw.githubusercontent.com/SylvanRoe/rules/main/CK.conf) |
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

---

## CK 凭证获取合集订阅与引用地址

- **GitHub Raw 原生地址**:
  `https://raw.githubusercontent.com/SylvanRoe/rules/main/CK.conf`

### Quantumult X 配置示例
```ini
[rewrite_remote]
https://raw.githubusercontent.com/SylvanRoe/rules/main/CK.conf, tag=[CK] 凭证获取合集, update-interval=172800, opt-parser=true, enabled=false
```

合集内含 23 个服务的 Cookie 获取重写规则（另有 2 个来源已 404 未收入），默认停用，在 QX 内按需开启。抓到 Cookie 后请及时关闭。
