# Oligarchy

Billionaire-grade Linux. Zero-dollar pricing.

A champagne-on-charcoal theme for [Omarchy](https://omarchy.org) 4 (Quattro).

![Oligarchy desktop](screenshots/desktop.png)

## Install

Omarchy Menu → Install → Theme, then paste:

```
https://github.com/zuhaibullahbaig/omarchy-oligarchy-theme
```

## The idea

Supercars are not expensive because of how much is on them. They are
expensive because of how little disagrees. Consistent stitch pitch, even
shut lines, switchgear that feels identical whether you touch it on the
door or the console.

So Oligarchy is not a gold theme. It is a charcoal theme with a strict gold
budget and four rules that every surface obeys.

**One light source.** Every gradient in the system runs 135°, lit from the
upper left. The window borders, the bar's bottom edge, the focus ring on a
dropdown, the brushed arc in the wallpaper, and the ring in the boot splash
are all lit from the same place. Nothing contradicts it.

**Gold is rare.** Champagne appears on focus, selection, and urgency. That
is the entire budget. Resting surfaces are neutral charcoal at low border
alpha. A theme where gold is scarce reads expensive; a theme where
everything is gold reads casino.

**One scale.** Spacing is a single multiplier over the shell's shared
rhythm, and the type scale hangs off one root size. There are no arbitrary
numbers.

**One signature.** Every surface that is selected, focused, or asking for
attention carries a champagne left edge with hairlines elsewhere. Menu rows,
launcher results, notifications, the clipboard, the emoji picker, the lock
field, polkit prompts. The same detail, everywhere, without exception.

![Omarchy menu](screenshots/menu.png)

The terminal is the one room allowed to be loud. Its palette is saturated
enough to carry `ls` output, syntax highlighting, and btop gauges, while the
shell chrome around it stays neutral.

## What it themes

| Layer | File |
| --- | --- |
| Palette, terminal, editors, btop, Chromium, window borders | `colors.toml` |
| Bar, controls, menu, launcher, popups, tooltip, notifications, lock, polkit, image picker, spacing, type | `shell.toml` |
| Theme switcher carousel | `preview.png` |
| Boot splash mark and preview | `unlock.png`, `preview-unlock.png` |
| File manager icons | `icons.theme` |
| Wallpapers | `backgrounds/` |

The boot splash is selectable under Style → Unlock. Wallpapers cycle with
Super + Ctrl + Space.

## Palette

| Role | Value |
| --- | --- |
| Accent | `#ffc84d` |
| Background | `#0a0c10` |
| Foreground | `#e4e7ec` |
| Selection | `#3a2e17` |
| Muted | `#737c8a` |

The background ramp runs `#050609` → `#080a0d` → `#0a0c10` → `#14171c`,
strictly darkest to lightest, so depth is never ambiguous. The terminal
palette is deliberately the highest-chroma thing in the system: `ls`, syntax
highlighting, diffs and btop gauges are working colour, not decoration.

## Regenerating the assets

Every image ships alongside the code that made it, so the artwork follows
the palette instead of drifting away from it.

```
python3 tools/render_assets.py
```

Requires Pillow and NumPy. It draws the ring mark, the boot splash, and the
default wallpaper from the palette constants at the top of the file — the arc
is shaded by a Lambert term against the same 135° vector the window borders
use, so the artwork cannot drift out of sync with the theme.

## A note on fonts

Omarchy takes its font from the fontconfig `monospace` alias, which a theme
cannot set — Oligarchy tunes the type *scale* instead. Pick the face yourself
under Style → Font. Anything with open apertures and a tall x-height suits
this palette; Maple Mono, Berkeley Mono, and JetBrains Mono all work well.

## License

MIT
