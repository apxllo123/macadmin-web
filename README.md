# Mac Admin Proposal

An evidence-first static GitHub Pages site presenting a responsible case for
administrator access on a personally purchased Mac used for software
development.

## Purpose

This project is a presentation site, not a bypass guide. It explains:

- practical limitations of a standard macOS account for development;
- concrete Apple-documented development operations that can require elevated
authorization;
- the real security and parental-control concerns around administrator access;
- the commitments and accountability proposed in response to those concerns;
- primary-source Apple documentation supporting the technical claims.

The site intentionally does **not** provide instructions for bypassing Screen
Time, Family Sharing, parental controls, or other restrictions.

## Current site

- Evidence-first proposal layout
- Primary-source evidence matrix
- Concrete Xcode and Command Line Tools examples
- Direct Apple Support and Apple Developer links
- GitHub repository link and GitHub branding
- Original macOS settings mockups in `resources/`
- Clear distinction between evidence, interpretation, and personal commitments
- Responsive cards and typography
- Static HTML/CSS suitable for GitHub Pages
- Automated GitHub Actions checks for HTML, documentation, links, local assets,
browser rendering, images, and oversized files

## Evidence standards

The strongest claims on this site are intentionally narrow.

Apple documents that some Mac tasks require an administrator name and password.
Apple also documents that administrators can add and manage users, install apps,
and change settings, while standard users can install apps and change their own
settings but cannot manage other users.

For development specifically, Apple documents the Command Line Tools package at
`/Library/Developer/CommandLineTools` and states that selecting an active Xcode
developer directory with `xcode-select --switch` requires superuser permissions.
Apple also documents tools such as `xcodebuild`, `devicectl`, and `xctrace` as
part of the Xcode command-line toolchain.

The site does **not** claim that every programming task needs administrator
access, that every `.dmg` requires administrator access, or that administrator
access is incapable of affecting parental controls.

## Primary sources

- [Apple Support: administrator authorization](https://support.apple.com/en-hk/guide/mac-help/mhosxlogo1438/mac)
- [Apple Support: Users & Groups](https://support.apple.com/en-ca/guide/mac-help/mtusr001/mac)
- [Apple Support: account permissions](https://support.apple.com/en-euro/guide/mac-help/mchl3e281fc9/mac)
- [Apple Support: help your child set up a Mac](https://support.apple.com/en-us/102142)
- [Apple Developer: installing Command Line Tools](https://developer.apple.com/documentation/xcode/installing-the-command-line-tools/)
- [Apple Developer: configuring Command Line Tools](https://developer.apple.com/documentation/xcode/configuring-command-line-tools-settings)
- [Apple Developer: Xcode command-line tools](https://developer.apple.com/documentation/xcode/xcode-command-line-tool-reference)
- [GitHub Docs: GitHub Pages publishing](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## Visual resources

`resources/` contains original explanatory mockups. They are intentionally not
copied Apple screenshots and are labeled as such on the page.

```text
resources/
├── developer-admin-mockup.svg
├── screen-time-mockup.svg
└── users-groups-mockup.svg
```

The SVG versions are the production visuals used by the site because they stay
sharp at any resolution. They can also be exported to PNG when a document or
presentation needs a raster image.

## Development workflow

`main` is the production and GitHub Pages branch.

`dev` is the single development branch. Experimental work should be made on
`dev` first and reviewed before it is moved to `main`.

Do **not** create any additional branches, including temporary or merge
branches. The conventional prefixes describe the **commit message**, not the
branch name.

Examples:

```text
feat: improve evidence section
fix: repair mobile spacing
docs: update source references
chore: clean up page metadata
```

Keep commits focused and easy to understand. Do not mix unrelated UI redesigns,
documentation, deployment changes, and experiments in one commit unless they
are genuinely one logical change.

## Verification

The repository includes `.github/workflows/site-checks.yml`.

The workflow runs on pushes and pull requests for `main` and `dev` and checks:

1. HTML structure and required document elements.
2. Local image references and local links.
3. HTML validity with `html-validate`.
4. README Markdown linting.
5. README and HTML external links with Lychee.
6. A real Chromium render of the page.
7. Broken image detection, browser console errors, page errors, and failed
external requests during rendering.
8. Oversized files that could accidentally bloat a static site.

Before moving a change from `dev` to `main`, review the visual result at desktop
and mobile widths and confirm the GitHub Pages deployment is healthy.

## Design principles

- Prefer clear sections over one large block of text.
- Keep evidence visually separate from personal promises.
- Use restrained Apple-like spacing and hierarchy without implying the site is
official Apple property.
- Keep source links visible and easy to verify.
- Favor accessibility and responsive behavior over decorative complexity.
- Avoid manipulative language. The goal is a transparent proposal based on
evidence and accountability.

## Publishing

The production branch is `main` and is intended for GitHub Pages.

Changes should be developed on `dev`, checked by GitHub Actions, reviewed, and
then moved to `main` only after approval.
