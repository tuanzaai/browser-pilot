# browser-pilot

Claude Code skill for browser automation — ask first, act later.

Based on [browser-act](https://www.browseract.com), enhanced with a **structured requirement clarification workflow** that ensures the AI understands your intent before touching the browser.

## What's different from browser-act?

The original browser-act skill executes immediately. browser-pilot adds a **Step 0** — a pre-execution clarification phase that asks the right questions based on your task type:

- **Target** — what site, what action (scrape vs. interact)?
- **Identity** — need login? multi-account isolation?
- **Output** — what data, what format (text/markdown/screenshot/JSON)?
- **Environment** — anti-bot protections? proxy? headed or headless?

When the intent is already clear (e.g. `browser-act browser list`), it skips straight to execution.

## Installation

### Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI
- Python 3.12+
- [uv](https://docs.astral.sh/uv/) package manager

### Install the skill

```bash
claude skill install --url https://github.com/tuanzaai/browser-pilot
```

### Install the browser-act CLI (first time only)

```bash
uv tool install browser-act-cli --python 3.12
```

## Usage

Once installed, the skill activates automatically in Claude Code when you:

- Mention `browser-pilot` or `browser-act` by name
- Ask to fetch/scrape/extract web content
- Ask to automate browser interactions (login, fill forms, click through workflows)
- Ask to take screenshots or capture network responses
- Ask to manage browser sessions

### Examples

```
> Help me scrape the pricing table from example.com

# browser-pilot will ask:
# - Do you need just the text or a screenshot too?
# - Is login required?
# - Any anti-bot protections on the site?
# Then executes the right browser-act commands.
```

```
> browser-act browser list

# Direct command — executes immediately, no clarification needed.
```

## Features

- **Requirement clarification** — understands your intent before acting, reducing errors and wasted runs
- **Lightweight extraction** — fast JS-rendered content fetch without a full browser session
- **Session management** — multi-browser isolation, multi-account parallel operation
- **Verification assistance** — handles interactive challenges with user authorization
- **Complex interaction** — DOM extraction, screenshots, form filling, file upload
- **Human-agent collaboration** — headed mode + remote assist for manual steps
- **Safety controls** — explicit user approval before browser creation, deletion, and sensitive operations

## Privacy & Security

- All cookies, sessions, credentials, and browser data stay **local** — never uploaded
- The only outbound data is the captcha challenge image when `solve-captcha` is invoked
- Sensitive operations (login, form submission, file upload) require explicit user confirmation

## License

MIT
