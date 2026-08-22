# Mac Admin Proposal

A polished static GitHub Pages site presenting a responsible case for
administrator access on a personally purchased Mac used for software
development.

## Purpose

This project is a presentation site, not a bypass guide. It explains:

- practical limitations of a standard macOS account for development;
- legitimate reasons administrator authorization can be needed;
- the real security and parental-control concerns around administrator access;
- the commitments and accountability proposed in response to those concerns;
- primary-source Apple documentation supporting the technical claims.

The site intentionally does **not** provide instructions for bypassing Screen
Time, Family Sharing, parental controls, or other restrictions.

## Current site

- Responsive section-based proposal layout
- Sticky navigation
- Distinct sections for the problem, development, trust, commitments,
  agreement, fairness, evidence, and final request
- Direct Apple Support and GitHub Pages source links
- Mobile-friendly cards and typography
- Clear separation between factual claims and personal commitments
- Static HTML/CSS suitable for GitHub Pages
- Automated GitHub Actions checks for HTML, documentation, links, local
  assets, and oversized files

## Development workflow

`main` is the production and GitHub Pages branch.

`dev` is the single development branch. Experimental work should be made on
`dev` first and reviewed before it is moved to `main`.

Do **not** create additional feature, fix, docs, or chore branches for this
project. The conventional prefixes describe the **commit message**, not the
branch name.

Examples:

```text
feat: improve evidence section
fix: repair mobile spacing
docs: update source references
chore: clean up page metadata
```

Keep commits focused and easy to understand. Do not mix unrelated UI
redesigns, documentation, deployment changes, and experiments in one commit
unless they are genuinely one logical change.

## Verification

The repository includes `.github/workflows/site-checks.yml`.

The workflow runs on pushes and pull requests for `main` and `dev` and checks:

1. HTML structure and required document elements.
2. Local image references and local links.
3. HTML validity with `html-validate`.
4. README and HTML external links with Lychee.
5. Oversized files that could accidentally bloat a static site.

Before moving a change from `dev` to `main`, also review the visual result at
desktop and mobile widths and confirm the GitHub Pages deployment is healthy.

## Design principles

- Prefer clear sections over one large block of text.
- Keep factual evidence visually separate from personal promises.
- Use restrained Apple-like spacing, typography, cards, and hierarchy without
  implying the site is an official Apple property.
- Keep source links visible and easy to verify.
- Favor accessibility and responsive behavior over decorative complexity.
- Avoid manipulative language. The goal is a transparent proposal based on
  evidence and accountability.

## Content principles

The strongest argument is not that administrator access is impossible to
misuse. That claim would be technically inaccurate.

Instead, the proposal acknowledges that administrators have broader permissions
and asks for a trust-and-accountability arrangement: legitimate development
access in exchange for explicit commitments and consequences for misuse.

## Repository structure

```text
macadmin-web/
├── .github/
│   └── workflows/
│       └── site-checks.yml
├── index.html
└── README.md
```

Keep the site lightweight and static. Add separate assets or page-specific
files only when they provide a clear benefit.

## Primary sources

The proposal currently references:

- Apple Support — administrator authorization on Mac
- Apple Support — standard and administrator user accounts
- Apple Support — guidance for setting up a Mac for a child
- GitHub Docs — configuring a GitHub Pages publishing source

Source URLs are kept directly in the site so readers can verify claims
independently.

## Publishing

The production branch is `main` and is intended for GitHub Pages.

Changes should be developed on `dev`, checked by GitHub Actions, reviewed, and
then moved to `main` only after approval.
