# aitools

Free, open-source tools for building with coding agents (Claude Code, Codex, Cursor and others), grouped by what they help with.

Every tool folder is a git submodule: a link to the original repository at a pinned commit. Nothing is copied or re-hosted, and each tool keeps its own licence.

<!-- tools:start -->

### Codebase context
Help your agent see how the whole repo connects before it changes anything.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Graphify**](https://github.com/Graphify-Labs/graphify)<br><sub>by Graphify Labs</sub> | Turns your codebase, SQL schemas, configs and docs into one knowledge graph your agent can query, so it sees what a change touches before it makes it. | Apache-2.0 | 153k | `uv tool install graphifyy && graphify install` |

### Agent workflow
Make the agent plan, test and change only what it should.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**last30days**](https://github.com/mvanhorn/last30days-skill)<br><sub>by mvanhorn</sub> | A skill that researches any person, company or topic across Reddit, X, YouTube, Hacker News, Polymarket and the web from the last 30 days and writes one brief ranked by real engagement. Reads a company's careers page too. | MIT | 74.6k | `/plugin marketplace add mvanhorn/last30days-skill   (then /plugin install last30days in Claude Code)`<br>`/last30days <company or topic>` |
| [**Plannotator**](https://github.com/backnotprop/plannotator)<br><sub>by backnotprop</sub> | Your coding agent's plans open in the browser: highlight, cross out and comment on steps, then send it all back in one click so the agent rewrites the plan before it touches code. Also reviews diffs and PRs. Runs locally. | Apache-2.0 | 15k | `curl -fsSL https://plannotator.ai/install.sh \| bash`<br>`/plugin marketplace add backnotprop/plannotator   (then /plugin install plannotator@plannotator in Claude Code)` |
| [**improve**](https://github.com/shadcn/improve)<br><sub>by shadcn</sub> | An Agent Skill: your most capable model audits the repo and writes self-contained plans, cheaper models execute them in an isolated worktree, and the big model reviews the diff. It never edits your code itself. | MIT | 12.2k | `npx skills add shadcn/improve`<br>`/improve   (then /improve execute 001 to hand a plan to a cheaper model)` |
| [**gstack**](https://github.com/garrytan/gstack) | Garry Tan's Claude Code setup: slash-command roles from CEO to QA. /review finds bugs that pass CI but fail in production, /qa tests in a real browser, /office-hours asks six forcing questions. | MIT | 143k | `git clone --single-branch --depth 1 https://github.com/garrytan/gstack.git ~/.claude/skills/gstack && cd ~/.claude/skills/gstack && ./setup` |
| [**Worktrunk**](https://github.com/max-sixty/worktrunk) | Git worktree CLI for parallel AI agents: each agent gets its own folder and branch (`wt switch -x claude -c <branch>`), and `wt merge` squashes, rebases, merges and cleans up. | Apache-2.0 | 12.7k | `brew install worktrunk && wt config shell install`<br>`winget install max-sixty.worktrunk` |
| [**mattpocock/skills**](https://github.com/mattpocock/skills) | Skills for real engineers. Includes grill-me: the agent interviews you about the plan, one round of recommended answers at a time, until nothing is left to guess. | MIT | 332k | `claude plugin install mattpocock-skills@claude-plugins-official`<br>`npx skills@latest add mattpocock/skills` |
| [**Superpowers**](https://github.com/obra/superpowers)<br><sub>by Jesse Vincent</sub> | A library of skills that makes the agent brainstorm, write a plan, work test-first in a git worktree and review itself before it calls a branch done. | MIT | 326k | `/plugin install superpowers@claude-plugins-official` |
| [**Karpathy-inspired CLAUDE.md**](https://github.com/multica-ai/andrej-karpathy-skills) | One CLAUDE.md built from Andrej Karpathy's notes on LLM coding mistakes: think before coding, keep it simple, make surgical changes, loop until tests pass. | see repo | 236k | `curl -o CLAUDE.md https://raw.githubusercontent.com/forrestchang/andrej-karpathy-skills/main/CLAUDE.md` |

### Agent memory
Let your agent remember past sessions instead of starting from zero.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**billion-context**](https://github.com/ranxianglei/billion-context) | Context compression for long agent sessions. Runs locally in front of the model API; the model folds old turns into detailed summaries and unfolds them when it needs the exact words. | see repo | 8.4k | `npm install -g billion-context`<br>`bili claude` |
| [**claude-mem**](https://github.com/thedotmack/claude-mem)<br><sub>by Alex Newman</sub> | Captures what your coding agent does, compresses each session into notes and injects the relevant ones next time. Stored in SQLite on your machine; note-writing uses a model (your plan, your key, or their hosted option). | Apache-2.0 | 120k | `npx claude-mem install` |

### Computer use
Let your agent operate apps and desktops that have no API.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**CLI-Anything**](https://github.com/HKUDS/CLI-Anything)<br><sub>by HKUDS</sub> | Makes desktop software agent-native: turns apps like LibreOffice, GIMP, Blender, OBS and Zoom into command-line tools your agent runs itself, no clicking. Install ready-made CLIs from its hub or build one for any app. | Apache-2.0 | 65.2k | `pip install cli-anything-hub && cli-hub install gimp`<br>`In Claude Code: /plugin marketplace add HKUDS/CLI-Anything, then /plugin install cli-anything` |
| [**AI YouTube Shorts Generator**](https://github.com/Anil-matcha/AI-Youtube-Shorts-Generator)<br><sub>by Anil-matcha (SamurAIGPT)</sub> | Open-source Opus Clip alternative: transcribes a long video or stream, scores every moment for hooks and emotional peaks with an LLM, and cuts the best into 9:16 shorts. No watermark, no per-clip credits. | MIT | 6.6k | `pip install -r requirements.txt && pip install -r requirements-local.txt`<br>`python main.py "stream.mp4" --mode local --num-clips 5   (OpenAI or Gemini key in .env)` |
| [**agent-desktop**](https://github.com/vercel-labs/agent-desktop) | Computer use for AI agents: reads desktop apps through the OS accessibility tree, so every button and field gets a ref to act on. Snapshot, act, snapshot again; runs in the background. macOS, Windows, Linux. | Apache-2.0 | 26.6k | `npm install -g agent-desktop` |

### Data and SQL
Give your agent the meaning of your data before it writes a query.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Claude Trading Skills**](https://github.com/tradermonty/claude-trading-skills)<br><sub>by tradermonty</sub> | 74 Claude Code skills for individual investors: market checks, risk limits, position sizing, a drawdown circuit breaker, journaling and a pre-trade discipline gate. Buy/sell decisions stay with you; not financial advice. | MIT | 8.4k | `git clone https://github.com/tradermonty/claude-trading-skills`<br>`cp -r claude-trading-skills/skills/pre-trade-discipline-gate ~/.claude/skills/   (repeat per skill)` |
| [**Sure**](https://github.com/we-promise/sure)<br><sub>by we-promise (community fork of Maybe Finance)</sub> | A full personal finance app you self-host for free: import bank statement CSVs, rules sort every transaction into categories, budgets show where the money went. Your data stays on your machine. | AGPL-3.0 | 17.8k | `curl -fsSL -o compose.yml https://raw.githubusercontent.com/we-promise/sure/main/compose.example.yml`<br>`docker compose up -d   (after setting SECRET_KEY_BASE and POSTGRES_PASSWORD in .env; then open localhost:3000)` |
| [**Auto-Ontology**](https://github.com/NVIDIA/auto-ontology) | Builds a map of what your database means (terms, reviewed SQL, safe joins) so agents look things up before writing SQL and say when the data can't answer. MCP server, 10 database engines, any OpenAI-compatible model. | Apache-2.0 | 14.9k | `git clone https://github.com/NVIDIA/auto-ontology.git && cd auto-ontology && docker compose up -d --build` |

### Cloud
Current, official instructions for the cloud platforms your agent builds on.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Google Agent Skills**](https://github.com/google/skills) | Google's official agent skills for Gemini API, Cloud Run, BigQuery, Firebase, GKE and 150+ more products. Pick the ones you need with npx skills, or install as Claude Code / Codex plugins. | Apache-2.0 | 24.6k | `npx skills add google/skills` |

### Security
Audit your code and the skills you install.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Open Code Review**](https://github.com/alibaba/open-code-review)<br><sub>by Alibaba</sub> | Alibaba's internal AI code reviewer, open-sourced: reads your Git changes or whole files and leaves line-level comments, with built-in rules for SQL injection, XSS and crashes. CLI or skills for Claude Code, Cursor, Codex. | Apache-2.0 | 56.2k | `npm install -g @alibaba-group/open-code-review && ocr config provider && ocr review`<br>`npx skills add alibaba/open-code-review   (skills for Claude Code, Cursor, Codex)` |
| [**Claude BugHunter**](https://github.com/elementalsouls/Claude-BugHunter)<br><sub>by elementalsouls (Sachin Sharma)</sub> | Skill bundle that turns Claude Code into a bug-bounty researcher: 83 skills and 15 commands built from 681 disclosed reports across 24 bug classes. Use on apps you own or are authorized to test. | MIT | 22k | `/plugin marketplace add elementalsouls/Claude-BugHunter`<br>`/plugin install claude-bughunter@elementalsouls` |
| [**AiSOC**](https://github.com/beenuar/AiSOC) | Self-hosted AI security operations center: groups related alerts into incidents, an agent investigates each one, every step goes into a ledger, and responses wait for approval. Runs a small local model with no API keys. | MIT | 7.8k | `git clone https://github.com/beenuar/AiSOC && cd AiSOC && make up` |
| [**SkillSpector**](https://github.com/NVIDIA/SkillSpector)<br><sub>by NVIDIA</sub> | Scans an agent skill for hidden instructions, key stealing and shady dependencies before you install it. 0-100 risk score. | Apache-2.0 | 27.6k | `uv tool install git+https://github.com/NVIDIA/skillspector.git` |
| [**Security Audit skill**](https://github.com/cloudflare/security-audit-skill)<br><sub>by Cloudflare</sub> | Runs a staged security audit of your codebase with any coding agent and writes verified findings. | MIT | 78.1k | `npx skills add https://github.com/cloudflare/security-audit-skill --skill security-audit` |

### Design
Stop shipping pages that look AI-generated.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Impeccable**](https://github.com/pbakaus/impeccable)<br><sub>by Paul Bakaus</sub> | A design vocabulary for your agent: steer UI with commands like bolder, quieter and polish, then critique and audit it to catch AI slop before it ships. | Apache-2.0 | 117k | `npx impeccable install`<br>`/impeccable init` |
| [**Hallmark**](https://github.com/Nutlope/hallmark)<br><sub>by Together AI</sub> | A design skill for Claude Code, Codex, Cursor and OpenCode that audits a page for the AI tells, then redesigns it. | MIT | 60.8k | `npx skills add nutlope/hallmark -g` |
| [**Taste Skill**](https://github.com/Leonxlnx/taste-skill)<br><sub>by Leon Lin</sub> | Gives the agent an art direction, real photos from open collections and a browser check, so new pages and app screens don't come out generic. | MIT | 121k | `/plugin marketplace add Leonxlnx/taste-skill`<br>`/plugin install taste-skill@taste-skill` |

### Testing
Keep agents honest about tests and CI.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**OpenSRE**](https://github.com/Tracer-Cloud/opensre)<br><sub>by Tracer-Cloud</sub> | Open-source CI/CD reliability agent: reads a failed CI run, separates flaky failures from broken code, traces the cause and pushes a fix for you to review. Also investigates production incidents. Self-hostable. | Apache-2.0 | 15.3k | `curl -fsSL https://install.opensre.com \| bash -s -- -gh`<br>`opensre   (then point it at the failing checks)` |
| [**App Store Compliance**](https://github.com/mjmirza/app-store-compliance)<br><sub>by mjmirza</sub> | Pre-submission guard for iOS and Android: scans your project against 117 documented App Store and Google Play rejection reasons in about a second, prints BLOCKED or CLEAR with fixes, and can stop uploads from your coding agent. | see repo | 6.1k | `git clone https://github.com/mjmirza/app-store-compliance ~/repositories/app-store-compliance`<br>`bash ~/repositories/app-store-compliance/agent-os/hooks/app-store-compliance-guard.sh "/path/to/your/app"` |
| [**Floci**](https://github.com/floci-io/floci) | Free local AWS emulator: point your SDK, CLI or Terraform at localhost:4566 and 100+ services (S3, DynamoDB, Lambda, SQS...) answer on your machine. No account, no auth token. | MIT | 32.1k | `floci start`<br>`docker run -d -p 4566:4566 floci/floci:latest` |
| [**CI test-count guard**](testing/ci-test-count-guard/)<br><sub>recipe in this repo</sub> | Rules for AGENTS.md plus a CI step that fails when the test count drops, so an agent can't delete failing tests to go green. | MIT |  | [setup](testing/ci-test-count-guard/README.md) |

### SEO
Audit how search engines and AI search see your site.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Claude SEO**](https://github.com/AgriciDaniel/claude-seo)<br><sub>by Agrici Daniel</sub> | An SEO audit toolkit for Claude Code: technical SEO, content quality, structured data and AI-search readiness. Optional extensions need your own third-party accounts. | MIT | 32.3k | `/plugin marketplace add AgriciDaniel/claude-seo`<br>`/plugin install claude-seo@agricidaniel-claude-seo`<br>`/seo setup` |

### Smart home
Let your agent read and change your home automations.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**ha-mcp**](https://github.com/homeassistant-ai/ha-mcp)<br><sub>by Unofficial Home Assistant AI Toolkit</sub> | An MCP server for Home Assistant: Claude, ChatGPT or any MCP client can read and change your automations, scenes, dashboards, lights, locks and cameras (87 tools). | MIT | 8.1k | `Home Assistant 2026.11+: Settings → Marketplace → HA-MCP → Install (2026.8+: HACS → HA-MCP)`<br>`Settings → Devices & Services → Add Integration → HA-MCP Server, then paste its connect URL into your AI client` |

### Career
Fix your CV and apply to fewer, better-fit jobs.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**career-ops**](https://github.com/career-ops-hq/career-ops)<br><sub>by santifer (career-ops-hq)</sub> | An open-source job search agent in your AI CLI: scans company job boards, scores each job against your CV and tells you to skip weak fits, tailors your CV and cover letter. You press Submit. | MIT | 84.7k | `npx @santifer/career-ops init`<br>`cd career-ops && claude   (then /career-ops scan)` |
| [**Reactive Resume**](https://github.com/reactive-resume/reactive-resume)<br><sub>by reactive-resume</sub> | A free, open-source, privacy-first resume builder: import your old CV or LinkedIn export, check it, export PDF, Word, Markdown or JSON. | MIT | 46.1k | `rxresu.me (free account) or self-host with Docker`<br>`Import → check → Export as Markdown for career-ops` |

<sub>34 tools · numbers from the GitHub API, synced 2026-11-25. Each linked folder is a git submodule pinned to the last checked commit.</sub>
<!-- tools:end -->

## Get the code
Every name in the tables links to the tool's own repository. To clone the tools as well:
```bash
git clone --recursive --shallow-submodules https://github.com/shikharjaiswal-in/aitools.git
```
A plain `git clone` gives just this list.

## Suggest a tool
Open an issue with the repository link and what it does. It must be free, open source and useful for building with coding agents.

## Licence
The README and the recipe folders are MIT. Each submodule is its authors' work under its own licence. Not affiliated with any company or tool listed.
