# keenan-inc brand reference

Direction **1A · Keystone**: a neutral stem with an accent chevron — a stencil K that stays legible at 16px. Accent: **teal**.

## Palette

Machine-readable source of truth: [`assets/brand/tokens/tokens.json`](../assets/brand/tokens/tokens.json).

### Accent
| Token | Hex | Use |
| :--- | :--- | :--- |
| `accent.light` | `#0F6E63` | Accent on white / GitHub light. 4.9:1 on `#FFFFFF`. |
| `accent.dark` | `#2FA694` | Accent on `#0D1117`. 6.6:1 on dark. |
| `accent.pressLight` / `pressDark` | `#0A5049` / `#43BFAC` | Hover / pressed states. |
| `accent.subtleLight` / `subtleDark` | `#E6F1EF` / `#0B2B27` | Tinted fills, callouts. |

### Neutrals
| Token | Hex | | Token | Hex |
| :--- | :--- | :-- | :--- | :--- |
| `ink.900` | `#0D1117` | | `gray.500` | `#6E7681` |
| `ink.800` | `#161B22` | | `gray.400` | `#8B949E` |
| `ink.700` | `#21262D` | | `gray.200` | `#C9D1D9` |
| `ink.600` | `#30363D` | | `paper.50` | `#F0F3F6` |
| `ink.500` | `#484F58` | | `paper.25` | `#F6F8FA` |
| `text.onLight` | `#14181D` | | `paper.0` | `#FFFFFF` |

### State
`state.ok #2FA694` · `state.warn #C9A227` · `state.risk #C4534B` · `state.info #7D6BB0`

Rules: never more than one accent per surface; no gradients; state colors only for status, never decoration.

## Typography

- **Sans (wordmark, UI, headings):** system grotesk stack — `-apple-system, BlinkMacSystemFont, "Segoe UI", "Helvetica Neue", Helvetica, Arial, sans-serif`. Wordmark is weight 500, tracking `-0.02em`, lowercase.
- **Mono (labels, badges, metadata, code):** `ui-monospace, SFMono-Regular, "SF Mono", Menlo, Consolas, monospace`. Labels are uppercase, 11–13px, tracking `0.22em`.
- No webfonts anywhere, so every SVG is self-contained and renders identically inside GitHub's sanitizer.

## Logo rules

| Asset | File | Use |
| :--- | :--- | :--- |
| Mark | `logo/mark-{dark,light}.svg` | Transparent, 64×64 grid. Inline in prose, footers, favicons. |
| Avatar | `logo/avatar-{dark,light}.svg` | Tiled 12px-radius background. Org avatar, app icons. |
| Wordmark | `logo/wordmark-{dark,light}.svg` | Horizontal lockup, 420×64. Docs headers, sites. |
| Banner | `banner/org-banner-{dark,light}.svg` | 1280×320 org header. |

- Clear space: one stem-width (6 units of the 64 grid) on all sides.
- Minimum sizes: mark 16px, wordmark 140px wide, banner 640px wide.
- Do not: recolor the chevron to a state color, outline the mark, add shadows or gradients, stretch, or place the mark on a mid-tone photo without the avatar tile.

## Badge style guide (shields.io)

Every badge, every repo, identical params:

```
style=flat-square
labelColor=21262D
color=0F6E63          # accent.light — legible in both GitHub themes
```

Status-carrying badges may swap `color` only to a state token:

| Meaning | color |
| :--- | :--- |
| stable / live / passing | `0F6E63` |
| beta | `0F6E63` |
| alpha / wip | `C9A227` |
| experimental | `6E7681` |
| deprecated / failing | `C4534B` |

Canonical row (in this order): **CI → version → license → platform**.

```markdown
![CI](https://img.shields.io/github/actions/workflow/status/keenan-inc/REPO/ci.yml?style=flat-square&labelColor=21262D&color=0F6E63&label=ci)
![Version](https://img.shields.io/github/v/release/keenan-inc/REPO?style=flat-square&labelColor=21262D&color=0F6E63&label=version&display_name=tag&sort=semver)
![License](https://img.shields.io/github/license/keenan-inc/REPO?style=flat-square&labelColor=21262D&color=0F6E63&label=license)
![Platform](https://img.shields.io/badge/platform-macos%20%C2%B7%20windows%20%C2%B7%20linux-0F6E63?style=flat-square&labelColor=21262D)
```

Labels are lowercase; separate multi-values with `%20%C2%B7%20` (space · space). No logos unless the tech is the point, and then `logoColor=F0F3F6`.

## Assets directory layout

Lives in the org's special `.github` repo, so paths are stable and referenceable from every other repo.

```
keenan-inc/.github/
├── profile/
│   └── README.md                  # org profile page
├── docs/
│   ├── BRAND.md                   # this file
│   ├── README-TEMPLATE.md         # repo README template
│   ├── APPLY-README.md            # mechanical instructions for Claude Code
│   └── LABELS.md                  # issue label palette
├── labels.yml                     # machine-readable label set
└── assets/
    └── brand/
        ├── logo/                  # mark, avatar, wordmark  ×{dark,light}
        ├── banner/                # org-banner, project-banner.template  ×{dark,light}
        ├── social/                # org + project social previews  ×{dark,light}
        └── tokens/tokens.json     # palette + type tokens
```

**Naming convention:** `<asset>[.template]-<scheme>.<ext>` — lowercase kebab-case, `-dark`/`-light` suffix always last, `.template` marks a file containing `{{TOKEN}}` placeholders. Never rename or move a published file; add a new one and deprecate.

**Stable raw base:**
```
https://raw.githubusercontent.com/keenan-inc/.github/main/assets/brand/
```
