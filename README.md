# specsmith-agent

An [opencode](https://opencode.ai) agent that turns rough ideas into detailed, well-structured task specifications for the [Agent Loops](https://github.com/danifernandezs/agent-loops) orchestration system.

## What it does

Takes a vague concept like *"a website for my project"* and produces a production-ready spec with:

- Exact tech stack and versions
- File structure and naming conventions
- Component/page/feature breakdowns
- Content schemas and requirements
- Styling details with hex codes and font names
- Concrete acceptance criteria with verification commands
- A ready-to-send `curl` command for the Agent Loops API

## Installation

```bash
mkdir -p .opencode/agents
curl -o .opencode/agents/specsmith.md https://raw.githubusercontent.com/danifernandezs/specsmith-agent/main/specsmith.md
```

Or clone and copy:

```bash
git clone https://github.com/danifernandezs/specsmith-agent.git
mkdir -p .opencode/agents
cp specsmith-agent/specsmith.md .opencode/agents/
```

## Usage

In any project with opencode, ask specsmith to help you define a task:

```
Write me a spec for a REST API that manages inventory for a warehouse
```

```
I need a spec for a landing page for my SaaS startup, similar to vercel.com
```

Specsmith will:

1. Research the tech/domain if needed
2. Ask clarifying questions if critical info is missing
3. Write a detailed spec following its structure
4. Output a `curl` command ready to POST to your Agent Loops orchestrator

## Agent Loops API

Specs are formatted for the [Agent Loops](https://github.com/danifernandezs/agent-loops) API. The agent will ask you for:

- **Orchestrator URL** — your Agent Loops instance (e.g., `https://your-instance.example.com:3000`)
- **API credentials** — authentication token, if required by your setup

## License

This work is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

Please read the [LICENSE](LICENSE.txt) file for more details.
