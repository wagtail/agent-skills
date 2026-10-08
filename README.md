# Agent skills for Wagtail

Wagtail's official collection of expert skills for developers working on Wagtail projects.

## Chose your own adventure

Our skills are authored to help across a wide range of projects and only load when Wagtail is involved, but that’s not to say you have to load them all. We offer multiple options.

### Install via Wagtail CLI

**Our recommended approach**. Install one evergreen Wagtail skill plus [`wagtail-cli`](https://pypi.org/project/wagtail-cli/), and it will automatically load relevant information from pre-bundled skills files and live developer docs as needed. Install the CLI first:

```bash
# Permanent install:
uv tool install wagtail-cli
# One-off usage:
uvx --from wagtail-cli wt
# Done!
wt --help
```

And the one skill, globally or locally, compatible with all harnesses which follow the [Agent Skills](https://agentskills.io/) specification:

```bash
# Directly with the CLI, global:
mkdir -p ~/.agents/skills/wagtail && wt skills get wagtail > ~/.agents/skills/wagtail/SKILL.md
# Directly with the CLI, local:
mkdir -p .agents/skills/wagtail && wt skills get wagtail > .agents/skills/wagtail/SKILL.md
```

It’s also available as a plugin. To install it, follow the [Agent Plugins compatible clients](https://agent-plugins.org/compatible-clients) installation instructions, using this repository as the plugin source: `wagtail/wagtail-cli`. Here is an example with `copilot`:

```bash
copilot plugin marketplace add wagtail/wagtail-cli
copilot plugin install wagtail-cli@wagtail/wagtail-cli
# Should say:
# Plugin "wagtail-cli" installed successfully. Installed 1 skill.
```

### Install as skills files

This approach works with all harnesses compatible with the [Agent Skills](https://agentskills.io/) specification, but doesn’t provide the progressive loading and integration features offered by the Wagtail CLI. If this is right for you, manually copy the files or use a tool like the [Vercel Skills CLI](https://github.com/vercel-labs/skills):

```bash
npx skills add wagtail/agent-skills
```

### Install as a plugin

This approach works with [harnesses compatible with Agent Plugins](https://agent-plugins.org/compatible-clients), but only installs for one harness at a time. It installs all Wagtail skills, but doesn’t make them progressively loading as well as the Wagtail CLI does. If this is right for you, adapt those `copilot` steps to your harness:

```bash
copilot plugin marketplace add wagtail/agent-skills
copilot plugin install core@wagtail-agent-skills
# Should say:
# Plugin "wagtail-cli" installed successfully. Installed 5 skills.
```

