---
name: hyprland
description: >-
  This skill should be used when the user asks about "Hyprland configuration",
  "hyprland.lua", "hyprland.conf", "Hyprland Lua config", "hyprctl",
  "Hyprland keybinds", "Hyprland window rules", "Hyprland monitors",
  "Hyprland dispatchers", "Hyprland animations", "Hyprland workspaces",
  "Hyprland IPC", "Hyprland plugins", "hyprlock", "hypridle", "hyprpaper",
  "hyprcursor", "hyprpicker", "hyprsunset", "xdg-desktop-portal-hyprland",
  "Hyprland on NixOS", "Hyprland Home Manager", "Hyprland layouts",
  "Hyprland dwindle", "Hyprland master layout", "Hyprland FAQ",
  "Hyprland performance", "Hyprland Nvidia", "Hyprland screen sharing",
  "Hyprland special workspace", "Hyprland smart gaps",
  "Hyprland multi-monitor", "Hyprland tearing",
  or any topic related to configuring, troubleshooting, or extending the
  Hyprland Wayland compositor and its ecosystem tools.
version: 0.3.0
---

# Hyprland Documentation

Complete reference for the Hyprland Wayland compositor, auto-generated from the official wiki at https://wiki.hypr.land/.

The `references/` directory contains the full, unmodified wiki markdown from https://github.com/hyprwm/hyprland-wiki, updated daily.

## How to Use

1. Identify the topic from the user's question and read the matching reference file from the tables below.
2. Base answers on those files. If more detail is needed, fetch the latest docs from the raw GitHub URLs in Live Fetching.
3. **Since Hyprland 0.55, the config is Lua** (`~/.config/hypr/hyprland.lua`): `hl.config({...})`, `hl.bind(...)`, `hl.monitor({...})`, `hl.window_rule({...})`, `hl.on(...)`. The old hyprlang format (`hyprland.conf`) is deprecated. Check the user's version with `hyprctl version` when in doubt.
4. For Hyprland 0.54 and earlier, use hyprlang syntax and point the user to the versioned wiki at https://wiki.hypr.land/0.54.0/ (the reference files here track the current Lua docs).
5. Split configs use Lua `require("subdir/file")`, not the old `source =` keyword.
6. For NixOS users, note that `hyprpm` is unsupported on Nix — use Home Manager or the NixOS module for plugins.
7. For troubleshooting, check `references/faq.md` first.

## Reference Files

### Configuration

| Topic | File |
|-------|------|
| Config file basics, Lua syntax, require, LSP stubs | **`references/start.md`** |
| Variables / options (general, decoration, input, misc, etc.) | **`references/variables.md`** |
| Keybinds (hl.bind, flags, submaps) | **`references/binds.md`** |
| Dispatchers (hl.dsp.*, hl.dispatch) | **`references/dispatchers.md`** |
| Window rules and layer rules | **`references/window-rules.md`** |
| Monitor configuration | **`references/monitors.md`** |
| Autostart (hyprland.start event) | **`references/autostart.md`** |
| Animations and bezier curves | **`references/animations.md`** |
| Workspace rules and smart gaps | **`references/workspace-rules.md`** |
| Environment variables | **`references/environment-variables.md`** |
| Layouts (dwindle, master, scrolling, monocle, custom) | **`references/layouts.md`** |
| Lua scripting, events, timers (hl.on, hl.exec_cmd) | **`references/expanding-functionality.md`** |
| Per-device input config | **`references/devices.md`** |
| Notifications API | **`references/notifications.md`** |
| Performance tuning | **`references/performance.md`** |
| XWayland | **`references/xwayland.md`** |
| Screen tearing | **`references/tearing.md`** |
| Multi-GPU | **`references/multi-gpu.md`** |
| Virtual GPU | **`references/virtual-gpu.md`** |
| Permissions | **`references/permissions.md`** |
| Gestures | **`references/gestures.md`** |
| Uncommon tips and tricks | **`references/uncommon-tips-and-tricks.md`** |
| Example configurations | **`references/example-configurations.md`** |

### Tools

| Topic | File |
|-------|------|
| hyprctl CLI usage (eval, repl, batch) | **`references/hyprctl.md`** |
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
| Dev libraries (hyprtoolkit, hyprlang, hyprutils, aquamarine, etc.) | **`references/hypr-libraries.md`** |

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
| Useful utilities (bars, launchers, screenshots, systemd, etc.) | **`references/useful-utilities.md`** |
| Crashes and bugs | **`references/crashes-and-bugs.md`** |
| Contributing to Hyprland | **`references/contributing.md`** |

## Live Fetching

When reference files are insufficient, fetch the latest docs from raw GitHub:

```
https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/<Section>/<Page>.md
```

Examples:
- `https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/Configuring/Basics/Variables.md`
- `https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/Configuring/Advanced%20and%20Cool/Using-hyprctl.md`
- `https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/Hypr%20Ecosystem/hyprlock.md`
- `https://raw.githubusercontent.com/hyprwm/hyprland-wiki/main/content/Nix/Hyprland%20on%20NixOS.md`

## Quick Reference (Hyprland 0.55+, Lua config)

### Config file location
`~/.config/hypr/hyprland.lua` (or `$XDG_CONFIG_HOME/hypr/hyprland.lua`, override with `Hyprland --config`)

### Options
```lua
hl.config({
    general = {
        border_size = 2,
        gaps_in = 5,
    },
})
```
Multiple `hl.config()` calls are allowed; each updates only what it receives.

### Binds
```lua
hl.bind("SUPER + SHIFT + Q", hl.dsp.exec_cmd("firefox"))
hl.bind("SUPER + X", function()
    hl.dispatch(hl.dsp.window.float({ action = "toggle" }))
end)
```

### Autostart
```lua
hl.on("hyprland.start", function()
    hl.exec_cmd("waybar & hyprpaper")
end)
```

### Window rules
```lua
hl.window_rule({
    match = { class = "firefox" },
    opacity = 0.9,
    float = true,
})
```

### Monitors
```lua
hl.monitor({
    output = "DP-1",
    mode = "1920x1080@144",
    position = "0x0",
    scale = 1,
})
```

### Split config
```lua
require("conf/binds")      -- ~/.config/hypr/conf/binds.lua
```

### hyprctl runtime control
```sh
hyprctl reload
hyprctl eval 'hl.config({ general = { border_size = 3 } })'
hyprctl repl               # interactive Lua REPL
hyprctl --batch "..."
```

## Legacy (Hyprland 0.54 and earlier, hyprlang)

Old-style `~/.config/hypr/hyprland.conf`:

```ini
bind = MODS, key, dispatcher, params
general {
    border_size = 2
}
monitor = name, resolution@rate, position, scale
```

Full legacy docs: https://wiki.hypr.land/0.54.0/
