# Smart-Remote 订阅转换配置

这是一个自定义远程配置，专为 Mihomo、Clash 等网络代理软件设计，包含以下功能：

- **智能路由自动选择**：根据延迟和网络条件自动选择最优代理节点。
- **服务分流**：为不同的网络服务（如 AI、Google、Cloudflare、GitHub、YouTube 等）提供精准的流量分流。
- **节点过滤**：使用正则过滤掉包含“剩余流量”、“套餐到期”、“官网”等无效节点。
- **健康检查**：支持对代理节点进行延迟检测与故障转移。

### 右键复制使用
**[PC版](https://raw.githubusercontent.com/Vincent-A-Yang/SmartProxyRules/main/smart-remote.ini)**
**[Phone版](https://raw.githubusercontent.com/Vincent-A-Yang/SmartProxyRules/main/smart-remote-phone.ini)**
**[MiHomo版](https://raw.githubusercontent.com/Vincent-A-Yang/SmartProxyRules/main/smart-remote-mihomo.ini)**

### 规则功能

- **智能路由 (`🚀 智能路由`)**：根据服务的地理位置自动选择最佳节点。
- **故障转移 (`🛟 自动兜底`)**：如果当前节点超时，自动切换到下一个可用节点。
- **服务分流组**：
  - **AI 服务**（如 ChatGPT、OpenAI 等）
  - **Google**
  - **Cloudflare**
  - **GitHub**
  - **开发仓库**（如 Docker、Debian 等）
  - **YouTube 和 Netflix 流媒体**

### 节点过滤

`exclude_remarks` 正则表达式将过滤掉包含以下关键词的节点：

- 剩余流量、套餐到期、官网、公告、邮箱等垃圾节点。

### 健康检查

- 使用 `url-test` 和 `fallback` 对代理节点进行健康检查，确保节点的可用性。
- 节点的选择是基于延迟优选，若当前节点不可用，则切换到其他可用节点。

## 如何使用

1. **将 `smart-remote.ini` 文件上传到 GitHub**。
2. 获取文件的 raw 链接地址。
3. 在“自定义远程配置”中粘贴 GitHub 的 raw 链接地址，完成订阅转换。

## 注意事项

- **`exclude_remarks`** 仅对节点备注进行过滤，无法判断节点的实时可用性，仍然依赖于健康检查进行节点的在线检测。
- 当前配置中使用了 **MetaCubeX/meta-rules-dat** 和 **ACL4SSR** 提供的公共规则集，确保你的转换器支持这些公开规则。

## 许可

本项目基于 **MIT License** 开源。

