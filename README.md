# Chrome DevTools for DeepSeek Harness

在 DSH 会话里列出 Chrome 标签页、检查页面或截图。这个组合包通过 stdio 启动 [Chrome DevTools MCP](https://github.com/ChromeDevTools/chrome-devtools-mcp)，使用独立的浏览器数据目录。

## 安装

运行 DSH Host 的机器需要安装 Chrome、Node.js 和 npm，并能从 Host 的 PATH 运行 `npx`。首次启用会从 npm 下载 MCP 服务端。`1.0.0` 使用 `chrome-devtools-mcp@1.14.0`；该版本支持 Node 20.19+（20.x）、22.12+（22.x）或 23 及以上。

在 DSH 启用「自定义插件索引」，打开「插件 → 发现 → 添加索引源」，粘贴下面的地址，再选择 **Chrome DevTools → 安装** 并启用。

```text
https://raw.githubusercontent.com/robb3n/dsh-plugins/main/index.json
```

在该 profile 的新会话里输入「请实际调用 `mcp__chrome-devtools__list_pages`，列出 Chrome 的页面」。首次调用会启动 Chrome，空白标签页也会出现在结果里。

浏览器数据保存在当前系统用户的 `~/.cache/chrome-devtools-mcp/dsh-plugin-chrome-devtools/`。在 Linux 上按此默认配置启动 Chrome 需要图形显示环境。如果该 DSH profile 已经注册同名的 `chrome-devtools` MCP 服务，请先停用旧配置。
