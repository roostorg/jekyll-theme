---
title: ROOST Jekyll Theme
---

# {{ site.title }}

{{ site.description }}

This site is built with the theme itself, so it doubles as a preview. See the [kitchen sink]({{ '/kitchen-sink/' | relative_url }}) for how common content looks.

## Usage

Add the theme to your site's `_config.yml`:

```yaml
remote_theme: roostorg/jekyll-theme
plugins:
  - jekyll-remote-theme
```

Pages without a `layout` use the theme's `default` layout automatically on GitHub Pages.

## Configuration

All settings are optional.

| Setting | Default | Use |
|---------|---------|-----|
| `title` | Repository name | Site name in the page title and social previews |
| `description` | Repository description | Meta and social preview description |
| `theme-color` | `#24291a` | Browser UI color |
| `icon` | ROOST mark | Favicon, relative to the site root |
| `card` | None | 1920×960 social preview image, relative to the site root; pages can set their own |
| `source_url` | The site's GitHub repository | "Source Code" button in the header |
| `mastodon.url`, `mastodon.handle` | None | Mastodon verification and author attribution |

## Customizing

Any theme file can be overridden by adding a file at the same path to your site. To add your own styles or scripts without replacing anything, create `_includes/head-custom.html`:

```html
{% raw %}<link rel="stylesheet" href="{{ '/style.css' | relative_url }}">{% endraw %}
```

The brand colors and fonts are available as CSS custom properties, like `var(--roost-yellow)` and `var(--font-display)`.
