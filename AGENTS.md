# benthompsondev.github.io - agent instructions

Applies to Claude Code and Codex. The shared global core arrives separately.
Do not assume a parent workspace guide is present in a session started here.

## What this repo is

The public personal site for Ben Thompson, served at
<https://benthompsondev.github.io/> by GitHub Pages from `main`, repo root.

Its job is search identity: making it unambiguous that this Ben Thompson is
`@benthompsondev`, in Cambridge Ontario, working in healthcare IT systems,
PowerShell and Python automation, and DevOps. Content is derived from the
profile README in the `benthompsondev/benthompsondev` repo, which stays the
source material.

## Boundaries

- Static HTML and CSS only. No framework, no build step, no dependencies, no
  analytics, no third-party scripts. If a change seems to need a build step,
  stop and ask first.
- Keep claims accurate and links current. Do not add private paths, agent
  configuration, credentials, workplace details, or claims the linked repos do
  not support.
- Add a `sameAs` entry only for a public URL that has been fetched and verified
  as Ben's. An unverified profile link is worse than no link.
- `robots.txt` and the origin are shared with the project Pages sites
  (`/cloakscan/`, `/ledger-local-finance/`, `/wedding-50-50/`). A `Disallow`
  here affects those too.

## Verification

There is no test suite. Before pushing, check the delivered result, not just
the source:

```bash
curl -sI https://benthompsondev.github.io/
curl -s https://benthompsondev.github.io/robots.txt
curl -s https://benthompsondev.github.io/sitemap.xml
curl -s https://benthompsondev.github.io/ | grep -E 'canonical|og:|description'
```

Confirm the canonical URL, that no `noindex` appeared, that the JSON-LD still
parses, and that every changed link resolves.

## Push authority

For this repo only, when Ben asks for site, SEO, or portfolio work, default to
committing and pushing completed safe changes after the checks above, then
report what changed. Otherwise follow the global ask-before-push rule.
