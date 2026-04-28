# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A static HTML publishing system for Aetonet research reports. Files are hosted via GitHub Pages at `https://aetonet.github.io/research-and-findings/`. There is no build step, no framework, and no dependencies — raw HTML files served directly from the `main` branch root.

## Publishing a new report

1. Place the new HTML file in the repo root using the naming convention `N_slug.html` where `N` is the next number in sequence.
2. Add a card to `index.html` inside `<main>`, after the last `</a>`, before `</main>`:

```html
<a class="report-card" href="N_slug.html">
  <div class="report-number">N</div>
  <div class="report-meta">
    <h2>Full Report Title</h2>
    <span>Report Type</span>
  </div>
  <div class="arrow">&#8594;</div>
</a>
```

Valid report types: `Field Report` / `Audit` / `Blueprint` / `Analysis` / `Setup Report`

3. Commit and push:

```bash
git add N_slug.html index.html
git commit -m "Add report N: Title"
git push
```

4. Update the count at the bottom of `UPLOAD_GUIDE.md`.

GitHub Pages deploys within ~60 seconds of push.

## Current state

- Reports: 5 (next file starts with `6_`)
- Remote: `git@github.com:Aetonet/research-and-findings.git`
- Auth: SSH via `~/.ssh/id_ed25519_github`

## Report HTML design system

All reports share the same visual language. When creating or editing report HTML files, use these conventions:

- **Fonts** (loaded from Google Fonts): `Fraunces` for headings, `Manrope` for body, `JetBrains Mono` for metadata and code
- **CSS variables**: `--paper` `--ink` `--brick` `--mustard` `--sage` `--indigo` — defined in `:root` at the top of each file
- **Layout components**: `.masthead`, `.hero`, `section`, `.findings` (key/value grid), `.timeline` (numbered steps), `.outcome-row` (stat cards)
- The paper grain texture is applied via a `body::before` SVG filter — do not remove it

## .claude/settings.local.json

This file pre-approves git commands so Claude can run them without a permission prompt each time:

```json
{
  "permissions": {
    "allow": [
      "Bash(git add *)",
      "Bash(git commit -m ' *)",
      "Bash(git push *)"
    ]
  }
}
```

It is **machine-local** (gitignored) and applies only to this project folder. It does not affect other projects. To add more pre-approved commands, add entries to the `allow` array using the format `"Bash(command pattern)"`. For global permissions that apply to all projects, edit `~/.claude/settings.json` instead.
