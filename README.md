# aitools

Free, open-source tools for building with coding agents (Claude Code, Codex, Cursor and others), grouped by what they help with.

Every tool folder is a git submodule: a link to the original repository at a pinned commit. Nothing is copied or re-hosted, and each tool keeps its own licence.

<!-- tools:start -->

### Codebase context
Help your agent see how the whole repo connects before it changes anything.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Graphify**](https://github.com/Graphify-Labs/graphify)<br><sub>by Graphify Labs</sub> | Turns your codebase, SQL schemas, configs and docs into one knowledge graph your agent can query, so it sees what a change touches before it makes it. | Apache-2.0 | 147k | `uv tool install graphifyy && graphify install` |

### Agent workflow
Make the agent plan, test and change only what it should.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**improve**](https://github.com/shadcn/improve)<br><sub>by shadcn</sub> | An Agent Skill: your most capable model audits the repo and writes self-contained plans, cheaper models execute them in an isolated worktree, and the big model reviews the diff. It never edits your code itself. | MIT | 11.6k | `npx skills add shadcn/improve`<br>`/improve   (then /improve execute 001 to hand a plan to a cheaper model)` |
| [**gstack**](https://github.com/garrytan/gstack) | Garry Tan's Claude Code setup: slash-command roles from CEO to QA. /review finds bugs that pass CI but fail in production, /qa tests in a real browser, /office-hours asks six forcing questions. | MIT | 141k | `git clone --single-branch --depth 1 https://github.com/garrytan/gstack.git ~/.claude/skills/gstack && cd ~/.claude/skills/gstack && ./setup` |
| [**Worktrunk**](https://github.com/max-sixty/worktrunk) | Git worktree CLI for parallel AI agents: each agent gets its own folder and branch (`wt switch -x claude -c <branch>`), and `wt merge` squashes, rebases, merges and cleans up. | see repo | 12.5k | `brew install worktrunk && wt config shell install`<br>`winget install max-sixty.worktrunk` |
| [**mattpocock/skills**](https://github.com/mattpocock/skills) | Skills for real engineers. Includes grill-me: the agent interviews you about the plan, one round of recommended answers at a time, until nothing is left to guess. | MIT | 323k | `claude plugin install mattpocock-skills@claude-plugins-official`<br>`npx skills@latest add mattpocock/skills` |
| [**Superpowers**](https://github.com/obra/superpowers)<br><sub>by Jesse Vincent</sub> | A library of skills that makes the agent brainstorm, write a plan, work test-first in a git worktree and review itself before it calls a branch done. | MIT | 317k | `/plugin install superpowers@claude-plugins-official` |
| [**Karpathy-inspired CLAUDE.md**](https://github.com/multica-ai/andrej-karpathy-skills) | One CLAUDE.md built from Andrej Karpathy's notes on LLM coding mistakes: think before coding, keep it simple, make surgical changes, loop until tests pass. | see repo | 233k | `curl -o CLAUDE.md https://raw.githubusercontent.com/forrestchang/andrej-karpathy-skills/main/CLAUDE.md` |

### Agent memory
Let your agent remember past sessions instead of starting from zero.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**billion-context**](https://github.com/ranxianglei/billion-context) | Context compression for long agent sessions. Runs locally in front of the model API; the model folds old turns into detailed summaries and unfolds them when it needs the exact words. | see repo | 7.1k | `npm install -g billion-context`<br>`bili claude` |
| [**claude-mem**](https://github.com/thedotmack/claude-mem)<br><sub>by Alex Newman</sub> | Captures what your coding agent does, compresses each session into notes and injects the relevant ones next time. Stored in SQLite on your machine; note-writing uses a model (your plan, your key, or their hosted option). | Apache-2.0 | 117k | `npx claude-mem install` |

### Computer use
Let your agent operate apps and desktops that have no API.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**agent-desktop**](https://github.com/vercel-labs/agent-desktop) | Computer use for AI agents: reads desktop apps through the OS accessibility tree, so every button and field gets a ref to act on. Snapshot, act, snapshot again; runs in the background. macOS, Windows, Linux. | Apache-2.0 | 22.8k | `npm install -g agent-desktop` |

### Data and SQL
Give your agent the meaning of your data before it writes a query.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Auto-Ontology**](https://github.com/NVIDIA/auto-ontology) | Builds a map of what your database means (terms, reviewed SQL, safe joins) so agents look things up before writing SQL and say when the data can't answer. MCP server, 10 database engines, any OpenAI-compatible model. | Apache-2.0 | 12.3k | `git clone https://github.com/NVIDIA/auto-ontology.git && cd auto-ontology && docker compose up -d --build` |

### Cloud
Current, official instructions for the cloud platforms your agent builds on.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Google Agent Skills**](https://github.com/google/skills) | Google's official agent skills for Gemini API, Cloud Run, BigQuery, Firebase, GKE and 150+ more products. Pick the ones you need with npx skills, or install as Claude Code / Codex plugins. | Apache-2.0 | 24.1k | `npx skills add google/skills` |

### Security
Audit your code and the skills you install.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**AiSOC**](https://github.com/beenuar/AiSOC) | Self-hosted AI security operations center: groups related alerts into incidents, an agent investigates each one, every step goes into a ledger, and responses wait for approval. Runs a small local model with no API keys. | MIT | 7.6k | `git clone https://github.com/beenuar/AiSOC && cd AiSOC && make up` |
| [**SkillSpector**](https://github.com/NVIDIA/SkillSpector)<br><sub>by NVIDIA</sub> | Scans an agent skill for hidden instructions, key stealing and shady dependencies before you install it. 0-100 risk score. | Apache-2.0 | 25.7k | `uv tool install git+https://github.com/NVIDIA/skillspector.git` |
| [**Security Audit skill**](https://github.com/cloudflare/security-audit-skill)<br><sub>by Cloudflare</sub> | Runs a staged security audit of your codebase with any coding agent and writes verified findings. | MIT | 71.3k | `npx skills add https://github.com/cloudflare/security-audit-skill --skill security-audit` |

### Design
Stop shipping pages that look AI-generated.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Impeccable**](https://github.com/pbakaus/impeccable)<br><sub>by Paul Bakaus</sub> | A design vocabulary for your agent: steer UI with commands like bolder, quieter and polish, then critique and audit it to catch AI slop before it ships. | Apache-2.0 | 109k | `npx impeccable install`<br>`/impeccable init` |
| [**Hallmark**](https://github.com/Nutlope/hallmark)<br><sub>by Together AI</sub> | A design skill for Claude Code, Codex, Cursor and OpenCode that audits a page for the AI tells, then redesigns it. | MIT | 54.1k | `npx skills add nutlope/hallmark -g` |
| [**Taste Skill**](https://github.com/Leonxlnx/taste-skill)<br><sub>by Leon Lin</sub> | Gives the agent an art direction, real photos from open collections and a browser check, so new pages and app screens don't come out generic. | MIT | 114k | `/plugin marketplace add Leonxlnx/taste-skill`<br>`/plugin install taste-skill@taste-skill` |

### Testing
Keep agents honest about tests and CI.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Floci**](https://github.com/floci-io/floci) | Free local AWS emulator: point your SDK, CLI or Terraform at localhost:4566 and 100+ services (S3, DynamoDB, Lambda, SQS...) answer on your machine. No account, no auth token. | MIT | 31.6k | `floci start`<br>`docker run -d -p 4566:4566 floci/floci:latest` |
| [**CI test-count guard**](testing/ci-test-count-guard/)<br><sub>recipe in this repo</sub> | Rules for AGENTS.md plus a CI step that fails when the test count drops, so an agent can't delete failing tests to go green. | MIT |  | [setup](testing/ci-test-count-guard/README.md) |

### SEO
Audit how search engines and AI search see your site.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Claude SEO**](https://github.com/AgriciDaniel/claude-seo)<br><sub>by Agrici Daniel</sub> | An SEO audit toolkit for Claude Code: technical SEO, content quality, structured data and AI-search readiness. Optional extensions need your own third-party accounts. | MIT | 28.7k | `/plugin marketplace add AgriciDaniel/claude-seo`<br>`/plugin install claude-seo@agricidaniel-claude-seo`<br>`/seo setup` |

### Smart home
Let your agent read and change your home automations.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**ha-mcp**](https://github.com/homeassistant-ai/ha-mcp)<br><sub>by Unofficial Home Assistant AI Toolkit</sub> | An MCP server for Home Assistant: Claude, ChatGPT or any MCP client can read and change your automations, scenes, dashboards, lights, locks and cameras (87 tools). | MIT | 7.7k | `Home Assistant 2026.11+: Settings → Marketplace → HA-MCP → Install (2026.8+: HACS → HA-MCP)`<br>`Settings → Devices & Services → Add Integration → HA-MCP Server, then paste its connect URL into your AI client` |

### Career
Fix your CV and apply to fewer, better-fit jobs.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**career-ops**](https://github.com/career-ops-hq/career-ops)<br><sub>by santifer (career-ops-hq)</sub> | An open-source job search agent in your AI CLI: scans company job boards, scores each job against your CV and tells you to skip weak fits, tailors your CV and cover letter. You press Submit. | MIT | 82.3k | `npx @santifer/career-ops init`<br>`cd career-ops && claude   (then /career-ops scan)` |
| [**Reactive Resume**](https://github.com/reactive-resume/reactive-resume)<br><sub>by reactive-resume</sub> | A free, open-source, privacy-first resume builder: import your old CV or LinkedIn export, check it, export PDF, Word, Markdown or JSON. | MIT | 45.7k | `rxresu.me (free account) or self-host with Docker`<br>`Import → check → Export as Markdown for career-ops` |

<sub>24 tools · numbers from the GitHub API, synced 2026-11-13. Each linked folder is a git submodule pinned to the last checked commit.</sub>
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
