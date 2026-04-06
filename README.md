# Brandbase

A public repository of brand logos in SVG format, with a Claude skill for instant access.

## Usage

### With Claude Code

If you have the Brandbase skill installed, just ask:

> "Add the Spotify logo to my navbar"
> "I need the GitHub logo in dark mode"
> "Get the Apple wordmark"

Claude will find and fetch the right logo automatically.

### Manual

Browse the `brands/` directory or use the raw GitHub URL:

```
https://raw.githubusercontent.com/MassiveMassimo/brandbase/main/brands/{brand}/{brand}-24.svg
```

## Contributing

We welcome contributions! See the [Contributing Guide](template/CONTRIBUTING.md) for how to add a brand.

**Quick version:**
1. Fork this repo
2. Create `brands/{brand-slug}/` with at least `{brand-slug}-24.svg` and `guidelines.md`
3. Open a PR

## Format Policy

All logos are SVG. See [Contributing Guide](template/CONTRIBUTING.md#svg-only-policy) for details and the rare bitmap exception.

## License

MIT
