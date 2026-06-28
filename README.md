# browser-pilot

Claude Code skill for browser automation — ask first, act later.

Let AI fully understand what you need before opening the browser. Whether it's scraping data, automating login flows, or taking screenshots, browser-pilot clarifies your intent first, then executes precisely — no wasted runs, no guesswork.

## What can browser-pilot do for you?

- **Scrape any website** — extract text, tables, or structured data from JS-rendered pages, even those requiring login
- **Automate workflows** — login, fill forms, click through multi-step flows, handle file uploads
- **Capture everything** — screenshots, DOM content, XHR/fetch responses, HAR network logs
- **Multi-account parallel** — run isolated browser sessions for different accounts simultaneously
- **Handle anti-bot challenges** — verification assistance with your authorization when automation gets blocked
- **Human-agent collaboration** — switch to headed mode for manual steps, then hand back to automation

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
