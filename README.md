# browser-pilot

[English](#what-can-browser-pilot-do-for-you) | [中文](#browser-pilot-能为你做什么)

Claude Code skill for browser automation — ask first, act later.

---

## What can browser-pilot do for you?

Let AI fully understand what you need before opening the browser. Whether it's scraping data, automating login flows, or taking screenshots, browser-pilot clarifies your intent first, then executes precisely — no wasted runs, no guesswork.

- **Scrape any website** — extract text, tables, or structured data from JS-rendered pages, even those requiring login
- **Automate workflows** — login, fill forms, click through multi-step flows, handle file uploads
- **Capture everything** — screenshots, DOM content, XHR/fetch responses, HAR network logs
- **Multi-account parallel** — run isolated browser sessions for different accounts simultaneously
- **Handle anti-bot challenges** — verification assistance with your authorization when automation gets blocked
- **Human-agent collaboration** — switch to headed mode for manual steps, then hand back to automation

### Installation

#### Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- Python 3.12+
- [uv](https://docs.astral.sh/uv/) package manager

#### Install the skill

```bash
claude skill install --url https://github.com/tuanzaai/browser-pilot
```

#### Install the browser-act CLI (first time only)

```bash
uv tool install browser-act-cli --python 3.12
```

### Usage

Once installed, the skill activates automatically in Claude Code when you:

- Mention `browser-pilot` by name
- Ask to fetch/scrape/extract web content
- Ask to automate browser interactions (login, fill forms, click through workflows)
- Ask to take screenshots or capture network responses
- Ask to manage browser sessions

#### Examples

```
> Help me scrape the pricing table from example.com

# browser-pilot will ask:
# - Do you need just the text or a screenshot too?
# - Is login required?
# - Any anti-bot protections on the site?
# Then executes the right commands.
```

```
> browser-act browser list

# Direct command — executes immediately, no clarification needed.
```

### Features

- **Requirement clarification** — understands your intent before acting, reducing errors and wasted runs
- **Lightweight extraction** — fast JS-rendered content fetch without a full browser session
- **Session management** — multi-browser isolation, multi-account parallel operation
- **Verification assistance** — handles interactive challenges with user authorization
- **Complex interaction** — DOM extraction, screenshots, form filling, file upload
- **Human-agent collaboration** — headed mode + remote assist for manual steps
- **Safety controls** — explicit user approval before browser creation, deletion, and sensitive operations

### Privacy & Security

- All cookies, sessions, credentials, and browser data stay **local** — never uploaded
- The only outbound data is the captcha challenge image when `solve-captcha` is invoked
- Sensitive operations (login, form submission, file upload) require explicit user confirmation

---

## browser-pilot 能为你做什么？

在打开浏览器之前，先让 AI 充分理解你的需求。无论是抓取数据、自动化登录流程还是截图，browser-pilot 都会先澄清你的意图，再精准执行——不浪费运行次数，不靠猜。

- **抓取任意网站** — 从 JS 渲染的页面中提取文本、表格或结构化数据，支持需要登录的页面
- **自动化工作流** — 登录、填表、点击多步流程、文件上传
- **全面捕获** — 截图、DOM 内容、XHR/fetch 响应、HAR 网络日志
- **多账号并行** — 为不同账号运行隔离的浏览器会话
- **应对反爬机制** — 遇到验证码等挑战时，经你授权后协助完成
- **人机协作** — 切换到有头模式手动操作，再交还给自动化继续执行

### 安装

#### 前置条件

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- Python 3.12+
- [uv](https://docs.astral.sh/uv/) 包管理器

#### 安装 Skill

```bash
claude skill install --url https://github.com/tuanzaai/browser-pilot
```

#### 安装 browser-act CLI（仅首次需要）

```bash
uv tool install browser-act-cli --python 3.12
```

### 使用方式

安装后，在 Claude Code 中遇到以下场景时会自动激活：

- 提到 `browser-pilot`
- 要求抓取/提取网页内容
- 要求自动化浏览器交互（登录、填表、点击流程）
- 要求截图或捕获网络响应
- 要求管理浏览器会话

#### 示例

```
> 帮我抓取 example.com 的价格表

# browser-pilot 会先问你：
# - 只要文本还是也要截图？
# - 需要登录吗？
# - 网站有反爬机制吗？
# 确认后再执行。
```

```
> browser-act browser list

# 直接命令 — 立即执行，无需澄清。
```

### 功能特性

- **需求澄清** — 执行前先理解你的意图，减少错误和无效运行
- **轻量提取** — 无需打开完整浏览器会话，快速获取 JS 渲染内容
- **会话管理** — 多浏览器隔离，多账号并行操作
- **验证协助** — 经用户授权后处理交互式验证挑战
- **复杂交互** — DOM 提取、截图、表单填写、文件上传
- **人机协作** — 有头模式 + 远程协助，支持手动步骤介入
- **安全控制** — 浏览器创建、删除及敏感操作前需用户明确批准

### 隐私与安全

- 所有 Cookie、会话、凭证和浏览器数据均**本地存储**——绝不上传
- 唯一的外发数据是调用 `solve-captcha` 时的验证码图片
- 敏感操作（登录、表单提交、文件上传）需用户明确确认

---

## License

MIT
