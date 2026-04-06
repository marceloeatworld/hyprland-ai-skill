---
name: hyprland
description: >-
  This skill should be used when the user asks about "Hyprland configuration",
  "hyprland.conf", "hyprctl", "Hyprland keybinds", "Hyprland window rules",
  "Hyprland monitors", "Hyprland dispatchers", "Hyprland animations",
  "Hyprland workspaces", "Hyprland IPC", "Hyprland plugins", "hyprlock",
  "hypridle", "hyprpaper", "hyprcursor", "hyprpicker", "hyprsunset",
  "xdg-desktop-portal-hyprland", "Hyprland on NixOS", "Hyprland Home Manager",
  "Hyprland layouts", "Hyprland dwindle", "Hyprland master layout",
  "Hyprland FAQ", "Hyprland performance", "Hyprland Nvidia",
  "Hyprland screen sharing", "Hyprland special workspace",
  "Hyprland smart gaps", "Hyprland multi-monitor", "Hyprland tearing",
  or any topic related to configuring, troubleshooting, or extending the
  Hyprland Wayland compositor and its ecosystem tools.
version: 0.1.0
---

# Hyprland Documentation

Complete reference for the Hyprland Wayland compositor, auto-generated from the official wiki at https://wiki.hypr.land/.

The `references/` directory contains the full, unmodified wiki markdown from https://github.com/hyprwm/hyprland-wiki, updated daily.

## Directives

- Base all answers on the official Hyprland wiki documentation in the reference files below.
- Use the correct Hyprland config syntax (`hyprland.conf` format, NOT TOML/YAML/JSON).
- Distinguish between **keywords** (`exec-once`, `bind`, `monitor`, `source`, `env`) and **variables** (set inside category blocks like `general {}`, `decoration {}`, etc.).
- Show config examples using current syntax (category blocks, not flat `general:border_size` except in `hyprctl keyword` context).

## Reference Files

Identify the topic from the user's question, then read the matching reference file:

### Configuration

| Topic | File |
|-------|------|
| Variables (general, decoration, input, misc, cursor, render, etc.) | **`references/variables.md`** |
| Keybinds (bind, bindm, submaps, flags) | **`references/binds.md`** |
| Dispatchers (exec, workspace, focus, resize, setprop, etc.) | **`references/dispatchers.md`** |
| Window rules and layer rules | **`references/window-rules.md`** |
| Monitor configuration | **`references/monitors.md`** |
| Keywords (exec-once, source, env, per-device input) | **`references/keywords.md`** |
| Animations and bezier curves | **`references/animations.md`** |
| Workspace rules and smart gaps | **`references/workspace-rules.md`** |
| Environment variables | **`references/environment-variables.md`** |
| Layouts (dwindle, master, scrolling, monocle) | **`references/layouts.md`** |
| Performance tuning | **`references/performance.md`** |
| XWayland | **`references/xwayland.md`** |
| Screen tearing | **`references/tearing.md`** |
| Multi-GPU | **`references/multi-gpu.md`** |
| Permissions | **`references/permissions.md`** |
| Gestures | **`references/gestures.md`** |
| Starting Hyprland (login managers, uwsm) | **`references/start.md`** |

### Tools

| Topic | File |
|-------|------|
| hyprctl CLI usage | **`references/hyprctl.md`** |
| IPC sockets and events | **`references/ipc.md`** |

### Hypr Ecosystem

| Topic | File |
|-------|------|
| Hyprlock (screen lock) | **`references/hyprlock.md`** |
| Hypridle (idle management) | **`references/hypridle.md`** |
| Hyprpaper (wallpaper) | **`references/hyprpaper.md`** |
| Hyprlauncher (app launcher) | **`references/hyprlauncher.md`** |
| Hyprpicker (color picker) | **`references/hyprpicker.md`** |
| Hyprsunset (blue light filter) | **`references/hyprsunset.md`** |
| Hyprcursor (cursor themes) | **`references/hyprcursor.md`** |
| XDPH (xdg-desktop-portal-hyprland) | **`references/xdph.md`** |
| Hyprpolkitagent (polkit auth) | **`references/hyprpolkitagent.md`** |
| Hyprshutdown (shutdown utility) | **`references/hyprshutdown.md`** |
| Hyprsysteminfo (system info) | **`references/hyprsysteminfo.md`** |
| Hyprpwcenter (power management) | **`references/hyprpwcenter.md`** |
| Hyprland Qt support | **`references/hyprland-qt-support.md`** |

### Plugins

| Topic | File |
|-------|------|
| Plugin usage and development | **`references/plugins.md`** |

### Platform-Specific

| Topic | File |
|-------|------|
| NixOS / Nix / Home Manager | **`references/nix.md`** |
| Nvidia setup | **`references/nvidia.md`** |

### Help

| Topic | File |
|-------|------|
| FAQ and troubleshooting | **`references/faq.md`** |
| Getting started / installation | **`references/getting-started.md`** |
| Useful utilities (bars, launchers, etc.) | **`references/useful-utilities.md`** |
| Crashes and bugs | **`references/crashes-and-bugs.md`** |
| Contributing to Hyprland | **`references/contributing.md`** |

## Live Fetching

When reference files are insufficient, fetch the latest docs from raw GitHub:

```
https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/<Section>/<Page>.md
```

Examples:
- `https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/Configuring/Variables.md`
- `https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/Hypr%20Ecosystem/hyprlock.md`
- `https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/Nix/Hyprland%20on%20NixOS.md`

## Strategy

1. Identify the topic from the user's question.
2. Read the matching reference file from the tables above.
3. Answer directly with config examples in proper `hyprland.conf` syntax.
4. If more detail is needed, fetch from the corresponding raw GitHub URL.
5. For NixOS users, note that `hyprpm` is unsupported on Nix — use Home Manager or the NixOS module for plugins.
6. For troubleshooting, check **`references/faq.md`** first.

## Quick Reference

### Config file location
`~/.config/hypr/hyprland.conf` (or `$HYPRLAND_CONFIG`)

### Bind syntax
```ini
bind = MODS, key, dispatcher, params
```

### Variable syntax
```ini
general {
    border_size = 2
    gaps_in = 5
}
```

### Window rule syntax
```ini
windowrule {
    match:class = ^(firefox)$
    opacity 0.9
    float
}
```

### Monitor syntax
```ini
monitor = name, resolution@rate, position, scale
monitor = , preferred, auto, 1  # fallback
```

### hyprctl runtime changes
```sh
hyprctl keyword general:border_size 3
hyprctl dispatch workspace 2
hyprctl --batch "keyword general:gaps_out 10 ; dispatch workspace 3"
```
