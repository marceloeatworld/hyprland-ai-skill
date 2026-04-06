# Hyprland AI Skill

Auto-updated [Hyprland](https://hypr.land/) documentation for AI coding assistants.

Uses the open [Agent Skills](https://agentskills.io) standard (SKILL.md). Works with **33+ AI coding assistants** including Claude Code, Cursor, Windsurf, GitHub Copilot, OpenAI Codex, Gemini CLI, Amp, OpenCode, Cline, Aider, Goose, Roo Code, and [many more](https://agentskills.io/clients).

References are **auto-generated** daily from the official [hyprland-wiki](https://github.com/hyprwm/hyprland-wiki) repository via GitHub Actions.

## Install

### Quick start

Clone into whichever directory your AI tool reads context from:

```bash
# Cursor
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .cursor/skills/hyprland

# Windsurf
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .windsurf/skills/hyprland

# GitHub Copilot
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .github/copilot-instructions.d/hyprland

# Cline
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .cline/skills/hyprland

# Claude Code (global, all projects)
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git ~/.claude/skills/hyprland

# Claude Code (project-local)
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .claude/skills/hyprland

# OpenCode
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .opencode/skills/hyprland

# Aider
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .aider/skills/hyprland

# Amp
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .amp/skills/hyprland

# ForgeCode
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .forgecode/skills/hyprland

# Gemini CLI
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .gemini/skills/hyprland

# OpenAI Codex
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .agents/skills/hyprland

# Cross-agent standard (works with any Agent Skills compatible tool)
git clone https://github.com/marceloeatworld/hyprland-ai-skill.git .agents/skills/hyprland
```

### With the install script

```bash
curl -fsSL https://raw.githubusercontent.com/marceloeatworld/hyprland-ai-skill/main/install.sh | bash -s -- --claude
curl -fsSL https://raw.githubusercontent.com/marceloeatworld/hyprland-ai-skill/main/install.sh | bash -s -- --cursor
curl -fsSL https://raw.githubusercontent.com/marceloeatworld/hyprland-ai-skill/main/install.sh | bash -s -- --windsurf
curl -fsSL https://raw.githubusercontent.com/marceloeatworld/hyprland-ai-skill/main/install.sh | bash -s -- --copilot
curl -fsSL https://raw.githubusercontent.com/marceloeatworld/hyprland-ai-skill/main/install.sh | bash -s -- --opencode
curl -fsSL https://raw.githubusercontent.com/marceloeatworld/hyprland-ai-skill/main/install.sh | bash -s -- --amp
curl -fsSL https://raw.githubusercontent.com/marceloeatworld/hyprland-ai-skill/main/install.sh | bash -s -- --forgecode
curl -fsSL https://raw.githubusercontent.com/marceloeatworld/hyprland-ai-skill/main/install.sh | bash -s -- --custom /path/you/want
```

Run `./install.sh --help` for all options.

## Update

```bash
git -C <install-path> pull
```

The references are updated daily by GitHub Actions, so `git pull` always gives you the latest wiki content.

## What it covers

| Category | Topics |
|----------|--------|
| **Configuration** | Variables, keybinds, dispatchers, window rules, monitors, animations, workspace rules, layouts (dwindle/master/scrolling/monocle), environment variables, XWayland, tearing, multi-GPU, gestures, permissions |
| **hyprctl** | CLI commands, runtime config changes, IPC sockets, event handling |
| **Hypr Ecosystem** | hyprlock, hypridle, hyprpaper, hyprlauncher, hyprpicker, hyprsunset, hyprcursor, xdg-desktop-portal-hyprland, and more |
| **NixOS** | NixOS module, Home Manager, plugin management (hyprpm not supported on Nix) |
| **Troubleshooting** | FAQ, performance tuning, Nvidia, crashes and bugs |
| **Plugins** | Usage with hyprpm, manual loading, plugin development in C++ |
| **Getting Started** | Installation, master tutorial, useful utilities |

## How it works

```
User asks about Hyprland
        |
        v
AI reads matching reference file from references/
        |
        v
If more detail needed -> fetch latest from raw.githubusercontent.com
        |
        v
Answer with correct hyprland.conf syntax
```

The `SKILL.md` file acts as a routing table: it maps topics to reference files and provides fallback URLs for live fetching.

The `references/` directory contains the **full unmodified markdown** from the Hyprland wiki — not summaries.

## How references stay up to date

A [GitHub Actions workflow](.github/workflows/update-references.yml) runs daily:

1. Clones `hyprwm/hyprland-wiki` (shallow)
2. Runs `scripts/generate-references.sh` to regenerate all reference files
3. If anything changed, commits and pushes

You can also regenerate manually:

```bash
bash scripts/generate-references.sh
```

## Structure

```
hyprland-ai-skill/
├── SKILL.md                              # Main instruction file (topic -> reference map)
├── install.sh                            # Multi-tool install script
├── scripts/
│   └── generate-references.sh            # Fetches wiki and generates references
├── .github/workflows/
│   └── update-references.yml             # Daily auto-update from wiki
└── references/                           # Auto-generated from hyprland-wiki (40+ files)
    ├── .wiki-version                     # Source commit tracker
    ├── variables.md                      # All config variables
    ├── binds.md                          # Keybind syntax and flags
    ├── dispatchers.md                    # All dispatchers
    ├── window-rules.md                   # Window and layer rules
    ├── monitors.md                       # Monitor configuration
    ├── keywords.md                       # exec-once, source, env, per-device
    ├── animations.md                     # Animation tree and bezier curves
    ├── workspace-rules.md                # Workspace rules and smart gaps
    ├── hyprctl.md                        # hyprctl CLI reference
    ├── ipc.md                            # IPC sockets and events
    ├── environment-variables.md          # Env var reference
    ├── layouts.md                        # Dwindle, master, scrolling, monocle
    ├── hyprlock.md, hypridle.md, ...     # Ecosystem tools
    ├── nix.md                            # NixOS / Home Manager setup
    ├── nvidia.md                         # Nvidia setup
    ├── faq.md                            # FAQ and troubleshooting
    ├── plugins.md                        # Plugin usage and development
    └── ...
```

## Compatibility

Built on the open [Agent Skills](https://agentskills.io) standard (SKILL.md). Compatible with [33+ AI coding tools](https://agentskills.io/clients):

| Tool | Install path |
|------|-------------|
| **Cross-agent standard** | `.agents/skills/hyprland` |
| Claude Code (global) | `~/.claude/skills/hyprland` |
| Claude Code (project) | `.claude/skills/hyprland` |
| Cursor | `.cursor/skills/hyprland` |
| Windsurf | `.windsurf/skills/hyprland` |
| GitHub Copilot / VS Code | `.github/skills/hyprland` |
| OpenAI Codex | `.agents/skills/hyprland` |
| Gemini CLI | `.gemini/skills/hyprland` |
| Amp | `.amp/skills/hyprland` |
| OpenCode | `.opencode/skills/hyprland` |
| Cline | `.cline/skills/hyprland` |
| Aider | `.aider/skills/hyprland` |
| Goose | `.goose/skills/hyprland` |
| Roo Code | `.roo/skills/hyprland` |

For tools not listed, clone into whichever directory your tool reads context/rules from.

## Examples

```
> How do I set up keybinds for volume control?
> What window rules do I need for picture-in-picture?
> How do I configure dual monitors with different scales?
> Set up hyprlock with a blur background and clock
> How do I use Hyprland on NixOS with flakes?
> What IPC events can I listen to for workspace changes?
> How do I fix screen tearing in games?
> Configure smart gaps (no gaps with single window)
```

## Credits

- [Hyprland](https://hypr.land/) by Vaxry and contributors
- [Hyprland Wiki](https://github.com/hyprwm/hyprland-wiki)
