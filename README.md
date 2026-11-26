<div align="center">

# Awesome Unity AI

**A curated list of tools that let AI coding agents work inside the Unity Editor:<br>MCP bridges, CLIs, agent skills and editor assistants, compared side by side.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg)](LICENSE)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Last reviewed](https://img.shields.io/badge/last%20reviewed-2026--11-blue.svg)](#comparison-of-editor-bridges)

</div>

This list is about **developer-side AI**: tools that let Claude Code, Codex, Cursor, Copilot, Gemini CLI and other agents read, edit, run and test a Unity project. In-game AI (ML-Agents, Inference Engine, LLM-driven NPCs) is out of scope.

Every GitHub entry was checked against its repository: not archived, pushed within the last 12 months, with a stated license. Star and last-commit badges are live.

## Contents

- [How to choose](#how-to-choose)
- [Comparison of editor bridges](#comparison-of-editor-bridges)
- [MCP and CLI bridges](#-mcp-and-cli-bridges)
- [Agent skills and configs](#-agent-skills-and-configs)
- [Editor assistants](#-editor-assistants)
- [Docs and context tools](#-docs-and-context-tools)
- [Multi-engine game dev agents](#-multi-engine-game-dev-agents)
- [Learning resources](#-learning-resources)
- [Contributing](#contributing)
- [License](#license)

## How to choose

An **editor bridge** gives your agent hands inside a running Unity Editor: inspect the scene, create objects, edit assets, read the console, run tests. Most use [MCP](https://modelcontextprotocol.io), so they work with any MCP client; a few skip MCP and expose a CLI that the agent calls through skills. Quick picks:

- **Widest adoption and client support:** [MCP for Unity](https://github.com/CoplayDev/unity-mcp).
- **Playtesting with simulated keyboard and mouse input in Play Mode:** [Unity CLI Loop](https://github.com/hatayama/unity-cli-loop), [UnityMCP (isuzu-shiranui)](https://github.com/isuzu-shiranui/UnityMCP), [Funplay Unity MCP](https://github.com/FunplayAI/funplay-unity-mcp).
- **No Python or Node.js to install:** [UnityMCP (isuzu-shiranui)](https://github.com/isuzu-shiranui/UnityMCP), [Funplay Unity MCP](https://github.com/FunplayAI/funplay-unity-mcp), [unity-cli](https://github.com/youngwoocho02/unity-cli), [Unity CLI Loop](https://github.com/hatayama/unity-cli-loop) v3.
- **Your own C# methods as tools, even inside a built game:** [AI Game Developer](https://github.com/IvanMurzak/Unity-MCP).
- **Official Unity tooling:** [Unity MCP](https://docs.unity3d.com/Packages/com.unity.ai.assistant@2.6/manual/integration/unity-mcp-landing.html) (beta, needs a Unity AI subscription) plus the [Unity agent plugin](https://github.com/Unity-Technologies/unity-agent-plugin) skills.

## Comparison of editor bridges

| Project | Tools¹ | Play Mode input² | Stars | Last commit |
|:--|:--|:--|:--|:--|
| [MCP for Unity](https://github.com/CoplayDev/unity-mcp) | 50 | — | ![](https://img.shields.io/github/stars/CoplayDev/unity-mcp?style=flat&label=) | ![](https://img.shields.io/github/last-commit/CoplayDev/unity-mcp?style=flat&label=) |
| [AI Game Developer](https://github.com/IvanMurzak/Unity-MCP) | —³ | — | ![](https://img.shields.io/github/stars/IvanMurzak/Unity-MCP?style=flat&label=) | ![](https://img.shields.io/github/last-commit/IvanMurzak/Unity-MCP?style=flat&label=) |
| [MCP Unity](https://github.com/CoderGamester/mcp-unity) | 35 listed | Play / pause / step only | ![](https://img.shields.io/github/stars/CoderGamester/mcp-unity?style=flat&label=) | ![](https://img.shields.io/github/last-commit/CoderGamester/mcp-unity?style=flat&label=) |
| [Unity CLI Loop](https://github.com/hatayama/unity-cli-loop) | — | ✅ keyboard, mouse, UI, replay | ![](https://img.shields.io/github/stars/hatayama/unity-cli-loop?style=flat&label=) | ![](https://img.shields.io/github/last-commit/hatayama/unity-cli-loop?style=flat&label=) |
| [Unity MCP Server](https://github.com/AnkleBreaker-Studio/unity-mcp-server) + [plugin](https://github.com/AnkleBreaker-Studio/unity-mcp-plugin) | 268 | — | ![](https://img.shields.io/github/stars/AnkleBreaker-Studio/unity-mcp-server?style=flat&label=) | ![](https://img.shields.io/github/last-commit/AnkleBreaker-Studio/unity-mcp-server?style=flat&label=) |
| [UnityMCP (isuzu-shiranui)](https://github.com/isuzu-shiranui/UnityMCP) | — | ✅ pointer, keys, record, replay | ![](https://img.shields.io/github/stars/isuzu-shiranui/UnityMCP?style=flat&label=) | ![](https://img.shields.io/github/last-commit/isuzu-shiranui/UnityMCP?style=flat&label=) |
| [Funplay Unity MCP](https://github.com/FunplayAI/funplay-unity-mcp) | 185 (full profile) | ✅ input simulation | ![](https://img.shields.io/github/stars/FunplayAI/funplay-unity-mcp?style=flat&label=) | ![](https://img.shields.io/github/last-commit/FunplayAI/funplay-unity-mcp?style=flat&label=) |
| [unity-cli](https://github.com/youngwoocho02/unity-cli) | — | Enter / exit only | ![](https://img.shields.io/github/stars/youngwoocho02/unity-cli?style=flat&label=) | ![](https://img.shields.io/github/last-commit/youngwoocho02/unity-cli?style=flat&label=) |
| [GladeKit MCP](https://github.com/Glade-tool/glade-mcp) | 275 | — | ![](https://img.shields.io/github/stars/Glade-tool/glade-mcp?style=flat&label=) | ![](https://img.shields.io/github/last-commit/Glade-tool/glade-mcp?style=flat&label=) |
| [Unity MCP Pro](https://github.com/youichi-uda/unity-mcp-pro-plugin) | 280+ | — | ![](https://img.shields.io/github/stars/youichi-uda/unity-mcp-pro-plugin?style=flat&label=) | ![](https://img.shields.io/github/last-commit/youichi-uda/unity-mcp-pro-plugin?style=flat&label=) |
| [Unity MCP (official, beta)](https://docs.unity3d.com/Packages/com.unity.ai.assistant@2.6/manual/integration/unity-mcp-landing.html) | — | — | — | — |

<sub>
¹ Tool counts as stated in each README (November 2026); "—" means the README gives no number. "35 listed" is a count of the tools the README documents.<br>
² ✅ means the README documents simulated keyboard or mouse input during Play Mode. "—" means it is not documented; it may still be reachable through a code-execution tool.<br>
³ Any C# method becomes a tool with one attribute, and tools can also run inside a built game.
</sub>

## 🔌 MCP and CLI bridges

Everything in the table above, plus:

- [Advanced Unity MCP](https://github.com/codemaestroai/advanced-unity-mcp) - MCP bridge from Code Maestro with separate packages for Unity 2020-2022 and Unity 6; proprietary license. ![](https://img.shields.io/github/stars/codemaestroai/advanced-unity-mcp?style=flat&label=)

## 🧠 Agent skills and configs

- [Unity agent plugin](https://github.com/Unity-Technologies/unity-agent-plugin) - Unity's official plugin for Claude Code, Codex, Copilot CLI and others; the recommended way to get Unity's skills in Claude Code and Codex. ![](https://img.shields.io/github/stars/Unity-Technologies/unity-agent-plugin?style=flat&label=)
- [Unity Skills](https://github.com/Unity-Technologies/skills) - The same official skills packaged for any agent that installs from [skills.sh](https://skills.sh) (`npx skills add`). ![](https://img.shields.io/github/stars/Unity-Technologies/skills?style=flat&label=)
- [UnitySkills](https://github.com/Besty0728/Unity-Skills) - Editor automation over a local REST API, exposed to agents as a large skill set. ![](https://img.shields.io/github/stars/Besty0728/Unity-Skills?style=flat&label=)
- [unity-cli-skill](https://github.com/niqibiao/unity-cli-skill) - Zero-config skill that lets an agent control the Unity Editor from the command line. ![](https://img.shields.io/github/stars/niqibiao/unity-cli-skill?style=flat&label=)
- [Claude Unity Game Studio](https://github.com/IdoCohen560/claude-unity-game-studio) - Unity-focused adaptation of Claude Code Game Studios: a studio hierarchy of agents and skills for Claude Code. ![](https://img.shields.io/github/stars/IdoCohen560/claude-unity-game-studio?style=flat&label=)
- [Unity AI Workflow](https://github.com/devdavv/unity-ai-workflow) - Rules, agents, skills and slash commands for AI-first Unity 6.2+ development. ![](https://img.shields.io/github/stars/devdavv/unity-ai-workflow?style=flat&label=)
- [AI Agent Unity Rules](https://github.com/Common-ka/ai-agent-unity-rules) - Shared rule set for Unity 6.2+ that serves both Cursor and Claude Code. ![](https://img.shields.io/github/stars/Common-ka/ai-agent-unity-rules?style=flat&label=)

## 💬 Editor assistants

- [Unity AI](https://unity.com/products/ai) - Unity's official in-Editor assistant; its package also ships the official Unity MCP server.
- [Aura](https://www.tryaura.dev/) - Commercial AI agent for Unity and Unreal, formerly Coplay.

## 📚 Docs and context tools

- [Unity API MCP](https://github.com/Codeturion/unity-api-mcp) - Fast, accurate Unity API lookups so the agent stops reading source files to guess signatures. ![](https://img.shields.io/github/stars/Codeturion/unity-api-mcp?style=flat&label=)

## 🎮 Multi-engine game dev agents

Not Unity-specific, but they support Unity projects.

- [Claude Code Game Studios](https://github.com/Donchitos/Claude-Code-Game-Studios) - Turns Claude Code into a game studio of specialised agents and workflow skills; Godot, Unity and Unreal routes. ![](https://img.shields.io/github/stars/Donchitos/Claude-Code-Game-Studios?style=flat&label=)
- [Awesome Gamedev Agent Skills](https://github.com/gamedev-skills/awesome-gamedev-agent-skills) - Game-dev skills with a router for Godot, Unity, Unreal and more. ![](https://img.shields.io/github/stars/gamedev-skills/awesome-gamedev-agent-skills?style=flat&label=)
- [Everything Game Dev Code](https://github.com/MRCalderon3D/everything-game-dev-code) - Scaffold of agents, commands and skills for Unity, Unreal, Godot and HTML across several agent harnesses. ![](https://img.shields.io/github/stars/MRCalderon3D/everything-game-dev-code?style=flat&label=)
- [Genex Desktop](https://github.com/genex-games/genex-desktop) - Open-source desktop app for AI-native game development in Unity, Unreal, Godot and more, with local model support. ![](https://img.shields.io/github/stars/genex-games/genex-desktop?style=flat&label=)

## 📖 Learning resources

- [Unity AI: how to get started with MCP](https://unity.com/blog/unity-ai-mcp-how-to-get-started) - Unity's walkthrough for connecting external agents to the Editor.
- [MCP servers in game development explained](https://unity.com/blog/mcp-servers-game-development) - Unity's overview of what MCP is and where it fits.
- [Unity MCP documentation](https://docs.unity3d.com/Packages/com.unity.ai.assistant@2.6/manual/integration/unity-mcp-landing.html) - Setup, relay and client configuration for the official server.
- [Unity CLI documentation](https://docs.unity.com/en-us/unity-cli) - The official CLI many skills use to drive the Editor, install Editors and run builds.
- [Model Context Protocol](https://modelcontextprotocol.io) - The protocol behind most bridges in this list.
- [Agent Skills](https://agentskills.io) - The open skill format used by the skills repositories above.

## Contributing

Suggestions are welcome. Read the [contribution guidelines](CONTRIBUTING.md) first; they cover what fits the list and how to update the comparison table.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, the contributors have waived all copyright and related rights to this work. See [LICENSE](LICENSE).
