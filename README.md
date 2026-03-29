# jekyll-theme-lumen

A clean, zero-dependency Jekyll theme designed for multilingual project documentation sites. Features a glassmorphism-style UI, sticky frosted-glass navigation, responsive layout, and a structured page layout with Hero, Stats, and Cards sections.

## Features

- **Zero Jekyll theme dependencies** — pure HTML/Liquid/CSS, no gem theme required
- **Two layouts**: `default` (article) and `structured` (homepage / feature pages)
- **Built-in multilingual support** — locale-aware header pill and per-article language switch
- **Structured page components** — Hero, Stats grid, Cards, Quick-links, List sections via front matter
- **Responsive** — mobile-friendly at 980 px and 640 px breakpoints
- **Typography** — IBM Plex Sans, JetBrains Mono, Noto Sans SC (via Google Fonts)

## Quick Start

### As a git submodule

```bash
git submodule add https://github.com/JekyllNet/jekyll-theme-lumen.git themes/jekyll-theme-lumen
```

Copy the theme files into your Jekyll site:

```
_layouts/     ← default.html, structured.html
_includes/    ← site-head.html, site-header.html, site-footer.html,
                article-language-switch.html, structured-page.html
assets/css/   ← site.css
assets/brand/ ← logo.svg, favicon.svg  (replace with your own)
```

Then copy `_config.example.yml` as a reference for your `_config.yml`.

### As a remote theme (GitHub Pages)

Add to your `_config.yml`:

```yaml
remote_theme: JekyllNet/jekyll-theme-lumen
plugins:
  - jekyll-remote-theme
```

## Configuration

See [`_config.example.yml`](_config.example.yml) for all available options.

Key site-level settings:

| Key | Description |
|---|---|
| `title` | Site title (shown in header brand and footer) |
| `logo` | Path to brand logo SVG |
| `favicon` | Path to favicon SVG |
| `source_url` | GitHub repo URL (header dropdown + footer) |
| `locales` | Array of `{ code, root, label }` for the language-switch pill |

Navigation URLs and labels are set via Jekyll `defaults` in `_config.yml`. See the example file for the full list of `ui_*` keys.

## Structured Layout Front Matter

```yaml
layout: structured
hero:
  eyebrow: "Badge text"
  title: "Page headline"
  lead: "Short description"
  primary_label: "Get started"
  primary_url: /en/getting-started/
  secondary_label: "GitHub"
  secondary_url: https://github.com/...
  tags: ["Feature A", "Feature B"]
  code_title: "Install"
  code: "dotnet add package MyPackage"
  note_title: "Note"
  note_text: "Some helpful callout."

stats:
  - label: "Stat label"
    value: "42"

sections:
  - title: "Section title"
    description: "Section description"
    variant: cards   # or: quick-links, list
    columns: 3
    items:
      - title: "Card title"
        description: "Card body"
```

## License

MIT
