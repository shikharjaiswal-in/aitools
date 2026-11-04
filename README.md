# aitools

Free, open-source tools for building with coding agents (Claude Code, Codex, Cursor and others), grouped by what they help with.

Every tool folder is a git submodule: a link to the original repository at a pinned commit. Nothing is copied or re-hosted, and each tool keeps its own licence.

<!-- tools:start -->

### Codebase context
Help your agent see how the whole repo connects before it changes anything.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Graphify**](https://github.com/Graphify-Labs/graphify)<br><sub>by Graphify Labs</sub> | Turns your codebase, SQL schemas, configs and docs into one knowledge graph your agent can query, so it sees what a change touches before it makes it. | Apache-2.0 | 142k | `uv tool install graphifyy && graphify install` |

### Agent workflow
Make the agent plan, test and change only what it should.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**mattpocock/skills**](https://github.com/mattpocock/skills) | Skills for real engineers. Includes grill-me: the agent interviews you about the plan, one round of recommended answers at a time, until nothing is left to guess. | MIT | 312k | `claude plugin install mattpocock-skills@claude-plugins-official`<br>`npx skills@latest add mattpocock/skills` |
| [**Superpowers**](https://github.com/obra/superpowers)<br><sub>by Jesse Vincent</sub> | A library of skills that makes the agent brainstorm, write a plan, work test-first in a git worktree and review itself before it calls a branch done. | MIT | 312k | `/plugin install superpowers@claude-plugins-official` |
| [**Karpathy-inspired CLAUDE.md**](https://github.com/multica-ai/andrej-karpathy-skills) | One CLAUDE.md built from Andrej Karpathy's notes on LLM coding mistakes: think before coding, keep it simple, make surgical changes, loop until tests pass. | see repo | 229k | `curl -o CLAUDE.md https://raw.githubusercontent.com/forrestchang/andrej-karpathy-skills/main/CLAUDE.md` |

### Agent memory
Let your agent remember past sessions instead of starting from zero.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**claude-mem**](https://github.com/thedotmack/claude-mem)<br><sub>by Alex Newman</sub> | Captures what your coding agent does, compresses each session into notes and injects the relevant ones next time. Stored in SQLite on your machine; note-writing uses a model (your plan, your key, or their hosted option). | Apache-2.0 | 112k | `npx claude-mem install` |

### Computer use
Let your agent operate apps and desktops that have no API.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**agent-desktop**](https://github.com/vercel-labs/agent-desktop) | Computer use for AI agents: reads desktop apps through the OS accessibility tree, so every button and field gets a ref to act on. Snapshot, act, snapshot again; runs in the background. macOS, Windows, Linux. | Apache-2.0 | 13.2k | `npm install -g agent-desktop` |

### Security
Audit your code and the skills you install.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**AiSOC**](https://github.com/beenuar/AiSOC) | Self-hosted AI security operations center: groups related alerts into incidents, an agent investigates each one, every step goes into a ledger, and responses wait for approval. Runs a small local model with no API keys. | MIT | 7k | `git clone https://github.com/beenuar/AiSOC && cd AiSOC && make up` |
| [**SkillSpector**](https://github.com/NVIDIA/SkillSpector)<br><sub>by NVIDIA</sub> | Scans an agent skill for hidden instructions, key stealing and shady dependencies before you install it. 0-100 risk score. | Apache-2.0 | 24.2k | `uv tool install git+https://github.com/NVIDIA/skillspector.git` |
| [**Security Audit skill**](https://github.com/cloudflare/security-audit-skill)<br><sub>by Cloudflare</sub> | Runs a staged security audit of your codebase with any coding agent and writes verified findings. | MIT | 58.3k | `npx skills add https://github.com/cloudflare/security-audit-skill --skill security-audit` |

### Design
Stop shipping pages that look AI-generated.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Impeccable**](https://github.com/pbakaus/impeccable)<br><sub>by Paul Bakaus</sub> | A design vocabulary for your agent: steer UI with commands like bolder, quieter and polish, then critique and audit it to catch AI slop before it ships. | Apache-2.0 | 102k | `npx impeccable install`<br>`/impeccable init` |
| [**Hallmark**](https://github.com/Nutlope/hallmark)<br><sub>by Together AI</sub> | A design skill for Claude Code, Codex, Cursor and OpenCode that audits a page for the AI tells, then redesigns it. | MIT | 47.1k | `npx skills add nutlope/hallmark -g` |
| [**Taste Skill**](https://github.com/Leonxlnx/taste-skill)<br><sub>by Leon Lin</sub> | Gives the agent an art direction, real photos from open collections and a browser check, so new pages and app screens don't come out generic. | MIT | 110k | `/plugin marketplace add Leonxlnx/taste-skill`<br>`/plugin install taste-skill@taste-skill` |

### Testing
Keep agents honest about tests and CI.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Floci**](https://github.com/floci-io/floci) | Free local AWS emulator: point your SDK, CLI or Terraform at localhost:4566 and 100+ services (S3, DynamoDB, Lambda, SQS...) answer on your machine. No account, no auth token. | MIT | 28.9k | `floci start`<br>`docker run -d -p 4566:4566 floci/floci:latest` |
| [**CI test-count guard**](testing/ci-test-count-guard/)<br><sub>recipe in this repo</sub> | Rules for AGENTS.md plus a CI step that fails when the test count drops, so an agent can't delete failing tests to go green. | MIT |  | [setup](testing/ci-test-count-guard/README.md) |

### SEO
Audit how search engines and AI search see your site.

| Tool | What it does | Licence | Stars | Install |
|---|---|---|---|---|
| [**Claude SEO**](https://github.com/AgriciDaniel/claude-seo)<br><sub>by Agrici Daniel</sub> | An SEO audit toolkit for Claude Code: technical SEO, content quality, structured data and AI-search readiness. Optional extensions need your own third-party accounts. | MIT | 26.4k | `/plugin marketplace add AgriciDaniel/claude-seo`<br>`/plugin install claude-seo@agricidaniel-claude-seo`<br>`/seo setup` |

<sub>15 tools · numbers from the GitHub API, synced 2026-11-04. Each linked folder is a git submodule pinned to the last checked commit.</sub>
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
