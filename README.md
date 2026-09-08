# 🌙 内观日志 — 内向者的自我内探工具

> 体重波动因果健康分析仪 · 纯前端 PWA · 零成本 · 零追踪

记录你的身体与心理状态，发现体重波动的因果规律，提前调整行为与情绪。所有数据仅存本地浏览器，永不上传。

## ✨ 核心功能

- **极简录入**：每天2分钟，支持一键复制前一天记录
- **周期自动推断**：基于出血量标记自动划分经期/卵泡期/排卵期/黄体期，不依赖固定天数
- **分层相关性分析**：在周期阶段 × 睡眠 × 压力三层嵌套下计算各变量与体重差分的相关性
- **滞后归因**：点击某天体重，自动回溯3天找出最高相关前置因子
- **决策树规则发现**：自动输出类似"在黄体期且睡眠不足时，高碳水对体重影响显著"的规则
- **自然语言备注解析**：扫描备注关键词，自动归类为"高钠饮食""工作压力"等因子
- **认知收获→情绪→体重**：量化分析内向者自我内探对长期稳定性的影响
- **PWA 离线可用**：断网也能记录和查看历史，可"添加到主屏幕"作为独立应用

## 🚀 本地运行

直接用浏览器打开 `index.html` 即可。或启动本地服务器：

```bash
# Python
python3 -m http.server 8000

# Node.js
npx serve .
```

然后访问 `http://localhost:8000`。

## 📦 部署上线（三选一）

### 方案一：腾讯云 EdgeOne Pages（推荐，国内访问最快）

1. 注册腾讯云账号 → 进入 [EdgeOne 控制台](https://console.cloud.tencent.com/edgeone)
2. 选择「Pages」→「创建项目」
3. **拖拽上传**本目录所有文件（index.html, manifest.json, sw.js, icon-*.png）
4. 获得免费域名（如 `xxx.edgeone.app`）
5. 完成！可直接访问，国内用户延迟最低

> 公测期免费，无需备案，支持无限流量。

### 方案二：GitHub Pages

```bash
# 1. 创建 GitHub 仓库（如 neiguan-log）
# 2. 上传所有文件
git init && git add . && git commit -m "init" && git branch -M main
git remote add origin https://github.com/你的用户名/neiguan-log.git
git push -u origin main

# 3. 仓库 Settings → Pages → Source: main branch
# 4. 访问 https://你的用户名.github.io/neiguan-log/
```

### 方案三：Cloudflare Pages

1. 注册 Cloudflare 账号 → 进入 Pages
2. 连接 GitHub 仓库 或 直接上传文件
3. 部署完成，获得 `xxx.pages.dev` 域名

## 📁 文件说明

```
├── index.html              # 主应用（含所有功能逻辑）
├── manifest.json           # PWA 清单（应用名、图标、主题色）
├── sw.js                   # Service Worker（离线缓存）
├── icon-192.png            # 应用图标 192×192
├── icon-512.png            # 应用图标 512×512
├── icon-maskable-512.png   # 自适应图标
└── README.md               # 本文件
```

## 🔒 隐私说明

- 所有数据存储在浏览器的 localStorage 中，**不上传任何服务器**
- 无注册、无登录、无云同步
- 清除浏览器数据 = 清除所有记录（请定期导出备份）
- 支持离线使用（PWA Service Worker 缓存）

## 🛠 技术栈

- 纯 HTML + CSS + JavaScript（无框架依赖）
- Chart.js（图表渲染）
- PWA（manifest + service worker）
- localStorage（数据持久化）

## 📝 使用建议

- 每天固定时间记录（如早晨起床后），保持一致性
- 至少连续记录 7 天，洞察功能才能开始分析
- 认真写内心笔记和活动备注——这是关键词解析的数据源
- 每周导出一次数据备份

## 📄 License

MIT — 自由使用、修改、分发
