# dotfiles

Personal configuration files for a Wayland desktop environment on Arch Linux, managed under `.config/`.

## Stack

| Category | Application |
|---|---|
| Window manager / compositor | [Hyprland](https://hyprland.org/) |
| Terminal emulator | [Kitty](https://sw.kovidgoyal.net/kitty/) |
| Shell | [Fish](https://fishshell.com/) |
| Application launcher | [Rofi](https://github.com/davatorium/rofi) |
| Notification daemon | [Dunst](https://dunst-project.org/) |
| Screen lock | [Hyprlock](https://github.com/hyprwm/hyprlock) |
| Wallpaper manager | [swww](https://github.com/LGFae/swww) |
| Color scheme generator | [wal (pywal)](https://github.com/dylanaraps/pywal) |
| System monitor | [Btop](https://github.com/aristocratos/btop) |
| System info fetch | [Fastfetch](https://github.com/fastfetch-cli/fastfetch) |
| Code editor | [Zed](https://zed.dev/) |

## Layout

```
.config/
├── btop/          # Btop resource monitor config
├── dunst/         # Dunst notification daemon config
├── fastfetch/     # Fastfetch system info config
├── fish/          # Fish shell config (aliases, prompt, wal integration)
├── hypr/          # Hyprland window manager + Hyprlock screen locker configs
├── kitty/         # Kitty terminal config (wal theme, 70% opacity, blur)
├── rofi/          # Rofi launcher and wallpaper-picker themes
├── scripts/       # Helper shell scripts (see below)
└── zed/           # Zed editor settings
```

## Scripts

Custom scripts live in `.config/scripts/` and are wired to Hyprland keybinds:

| Script | Keybind | Description |
|---|---|---|
| `master.sh` | `SUPER + T` | Master menu — launch btop, edit configs, open settings, pick wallpaper, or run fastfetch |
| `power.sh` | `SUPER + L` | Power menu — lock, log out, reboot, or shut down |
| `wallpaper.sh` | via master menu | Wallpaper selector with thumbnails; applies theme via `wal` + `swww` |
| `config.sh` | via master menu | Opens any dotfile config in Zed |
| `settings.sh` | via master menu | Appearance settings — rounding, borders, gaps, animations |
| `animations.sh` | via settings menu | Switch workspace animation style (fade / vertical / horizontal) |

## Theming

All colors are driven by [pywal](https://github.com/dylanaraps/pywal). After selecting a wallpaper with `wallpaper.sh`, `wal` generates a color scheme from it and propagates the palette to Kitty, Rofi, and other supporting applications automatically.

## Key Hyprland Bindings

| Keybind | Action |
|---|---|
| `SUPER + Q` | Open terminal (Kitty) |
| `SUPER + C` | Close active window |
| `SUPER + R` | Application launcher (Rofi) |
| `SUPER + E` | File manager (Nautilus) |
| `SUPER + F` | Toggle fullscreen |
| `SUPER + T` | Master menu |
| `SUPER + L` | Power menu |
| `SUPER + Tab` | Switch workspace |
| `ALT + S` | Screenshot (grim + slurp) |

## System

- **OS:** Arch Linux
- **Package manager:** `pacman` + `yay` (AUR)
- **Display server:** Wayland
- **Monitors:** HDMI-A-1 @ 1920×1080 200 Hz (primary), DP-1 @ 1920×1080 144 Hz (secondary)