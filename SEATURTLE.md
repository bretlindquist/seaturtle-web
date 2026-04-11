# SEATURTLE.md

This file provides guidance to CT (ct) when working with code in this repository.

## Commands

This repository is currently a handcrafted static site with no package manager or checked-in JS build pipeline.

Common local workflow:

```bash
python3 -m http.server 4173
```

Then open <http://localhost:4173>.

There are currently no repo-defined lint or test commands.

Before adding tooling, prefer keeping the site lightweight unless the work clearly benefits from a framework or build step.

## High-level architecture

### Site architecture

The site is currently a single-page static landing site composed of:

- `index.html` — all page structure and copy
- `styles.css` — full visual system, layout, responsive behavior, and atmosphere
- `main.js` — small client-side enhancements only; currently copy-to-clipboard buttons for install commands
- `vercel.json` — minimal Vercel config using clean URLs
- `README.md` — lightweight local preview instructions

This is intentionally not a framework app yet. The current architecture favors direct control over voice, spacing, and composition.

### Content strategy

The page is structured as a short journey instead of a feature catalog:

1. atmospheric introduction
2. who SeaTurtle is
3. why it feels different
4. install path
5. closing CTA

That structure matters. The site should let visitors meet SeaTurtle before shifting into installation instructions.

### Relationship to `seaturtle-cli`

This site is a presentation layer for the nearby `seaturtle-cli` project, not the product runtime itself.

The current install guidance is based on the CLI repo's real source-build flow:

- clone `seaturtle-cli`
- run `./scripts/install-local-cli.sh --build`
- start with `ct`

If the CLI install flow changes, update the website copy to match the CLI README rather than letting the two drift.

### Design posture

This repo's `.ct/` files are part of the working architecture because they define how CT should shape design decisions here.

Key implications from the project-local guidance:

- keep the site warm, lightly playful, and non-generic
- preserve SeaTurtle's sense of presence without over-explaining hidden machinery
- improve hierarchy, spacing, rhythm, legibility, and responsive behavior before adding flourish
- avoid generic AI landing page patterns and overlong feature-grid sludge
- keep the install path clear, but do not flatten the personality out of the site

### Instruction routing

`CLAUDE.local.md` delegates to `.ct/router.md`, which layers the repo's private CT guidance:

- `.ct/soul.md`
- `.ct/identity.md`
- `.ct/role.md`
- `.ct/user.md`
- `.ct/attunement.md`
- `.ct/session.md`

For future CT instances, those files are important context for preserving the intended voice and UX quality bar of the site.

## What to preserve when editing

- The site should feel authored, not templated.
- Prefer a few strong sections over many shallow ones.
- Keep installation instructions concrete and real.
- If you introduce a framework later, update this file with the actual dev/build/test commands and the new architecture boundaries.
