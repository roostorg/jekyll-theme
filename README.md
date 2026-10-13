# jekyll-theme

A shared Jekyll theme for ROOST sites on [GitHub Pages](https://docs.github.com/en/pages), with ROOST brand colors, typography, header, and footer.

## Usage

Add the theme to your site's `_config.yml`:

```yaml
remote_theme: roostorg/jekyll-theme
plugins:
  - jekyll-remote-theme
```

GitHub Pages downloads the theme from this repo each time your site builds; there's nothing to install or copy. Pages without a `layout` use the theme's `default` layout automatically.

To guard against unexpected changes, you can pin a specific tag, branch, or commit, e.g. `roostorg/jekyll-theme@v1`.

### Configuration

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

### Customizing

Any file in [`_layouts/`](_layouts), [`_includes/`](_includes), or [`assets/`](assets) can be overridden by adding a file at the same path to your site.

To add your own styles or scripts without replacing anything, create `_includes/head-custom.html` in your site:

```html
<link rel="stylesheet" href="{{ '/style.css' | relative_url }}">
```

The brand colors and fonts are available as CSS custom properties, like `var(--roost-yellow)` and `var(--font-display)`.

## Local development

This repo is a Jekyll site that uses its own theme, so you can preview changes here directly.

1. **Prerequisites**: you'll need to install [Ruby](https://www.ruby-lang.org/en/documentation/installation/), [Bundler](https://bundler.io/), and [Jekyll](https://jekyllrb.com/docs/installation/).

2. **Project dependencies** are managed as Ruby gems with Bundler. Run `bundle install` to get everything set up the first time.

3. **Build and serve** the site locally with Jekyll using `bundle exec jekyll serve`, then navigate to [http://localhost:4000](http://localhost:4000).

To preview unreleased theme changes on another site, push them to a branch here, then point that site at it locally with an extra, uncommitted config file:

```yaml
# _config.dev.yml
remote_theme: roostorg/jekyll-theme@your-branch
```

```sh
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

Sites using the theme fetch it when `jekyll serve` starts, so they need a network connection, and a restart to pick up new theme changes.
