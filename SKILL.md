---
name: brandbase
description: Use when the user needs a brand logo, company icon, or brand asset for their project. Fetches SVG logos from the brandbase repository.
---

# Brandbase

Fetch brand logos from the [Brandbase](https://github.com/MassiveMassimo/brandbase) repository.

## Fetch Flow

When a user needs a brand logo, follow these steps exactly:

### Step 1: Normalize

Convert the brand name to a lowercase, hyphenated slug. Strip special characters, replace spaces with hyphens, lowercase everything:
- "VS Code" → `visual-studio-code`
- "GitHub" → `github`
- "Stack Overflow" → `stack-overflow`
- "YouTube" → `youtube`

If the slug is uncertain (abbreviations, special characters like C++, .NET, AT&T), try your best guess first — Step 2 will fall back to a directory search if it doesn't match.

### Step 2: Discover

List the contents of the brand folder to see what assets are available.

**Primary — GitHub MCP:**
If a GitHub MCP tool is available (e.g., `get_file_contents`), use it with owner `MassiveMassimo`, repo `brandbase`, path `brands/{slug}`.

**Fallback — WebFetch:**
If no GitHub MCP tool is available, use WebFetch on:
`https://api.github.com/repos/MassiveMassimo/brandbase/contents/brands/{slug}`
The response is JSON. Each entry has a `download_url` field — use that to fetch the raw file.

**If not found:**
List the `brands/` directory (same tool, path `brands`) and search for folder names containing the brand keyword. If still not found, tell the user the brand is not in Brandbase yet and link to the repo for contributions.

### Step 3: Select and Fetch

Review the folder listing and select the right file:

| Context | Selection |
|---------|-----------|
| No preference | `{brand}-24.svg` (default) |
| Dark background | `{brand}-{size}-dark.svg` if available |
| Specific size requested | `{brand}-{size}.svg` |
| Wordmark/logotype needed | `{brand}-wordmark.svg` |

Fetch the selected file using the same tool from Step 2, with the full file path (e.g., `brands/spotify/spotify-24.svg`).

If the user is doing design work (placing logo on backgrounds, building a brand page), also fetch `guidelines.md` from the brand folder for usage rules.

## Naming Convention

Files follow: `{brand}-{size}[-{variant}].svg`

- `{brand}` — lowercase, hyphenated, matches folder name
- `{size}` — pixel dimension (square): `24`, `48`, `96`
- `{variant}` — optional: `dark`, `light`, `wordmark`, `monochrome`

Every brand has at minimum `{brand}-24.svg` (24x24px square).
