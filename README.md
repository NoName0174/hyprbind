# hyprbind

A TUI to setup Hyprland binds for beginners.

## Features

- 4-step interactive pipeline: environment → select → customize → format
- Environment filter: plain Hyprland, quickshell, or both
- Paged TUI: scroll with q/e, navigate and toggle binds
- Customization: edit combo/mods/key/disp/arg/flags per bind, disable unwanted ones, session changelog
- Output formats: hyprland.conf (pre-0.55) or lua (latest)
- Non-interactive modes: --list, --all, number/range selection
- Dry-run: --test exercises the full pipeline without writing files

## Usage

```
Usage: hyprbind [OPTIONS] [SELECTION]

Options:
  --format conf   hyprland.conf output (default)
  --format lua    Lua config output
  -o, --output    Output directory (writes keybinds.conf or keybinds.lua)
  --list          Print bind numbers and descriptions
  --all           Generate all binds non-interactively
  --test          Dry-run the full interactive pipeline
  --help, -h      Show this message

Examples:
  hyprbind                                    TUI to stdout
  hyprbind --all -o ~/hypr/                   all binds to files
  hyprbind --list                             see numbers
  hyprbind 1,3,5-7,10                         pick by number
  hyprbind --format lua -o ~/hypr/            Lua output to files
  hyprbind --test                             dry-run full pipeline
```

## Pipeline

1. Environment — pick plain Hyprland / quickshell / both
2. Selection — paged TUI, toggle binds with numbers/ranges/all/none
3. Customization — edit fields, toggle enable/disable, review changes
4. Format — choose .conf or .lua

## Dependencies

- sh (POSIX)
- awk (POSIX)
