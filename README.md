# benthompsondev.github.io

The personal site for [Ben Thompson (@benthompsondev)](https://github.com/benthompsondev),
live at <https://benthompsondev.github.io/>.

It is one static page. No build step, no framework, no dependencies. GitHub
Pages serves the repo root as-is, so editing `index.html` and pushing to `main`
is the whole deploy process.

## Why it exists

Searching "Ben Thompson dev" turns up a lot of people. This site is the one
page that ties the name, the `benthompsondev` handle, the location, and the
actual projects together, so search engines have something unambiguous to point
at. It is also the parent page for the project sites already hosted on this
domain.

## Files

| File | What it does |
| --- | --- |
| `index.html` | The whole site. Content, CSS, and the ProfilePage/Person structured data |
| `robots.txt` | Allows crawling and points at the sitemap |
| `sitemap.xml` | The site root and indexable project pages on the same domain |
| `.nojekyll` | Skips Jekyll processing so Pages just serves the files |

## Open follow-ups

- **Google Search Console: verification file is in place, rest is manual.**
  `google0de73824cd6c6e23.html` sits in the repo root and serves at
  <https://benthompsondev.github.io/google0de73824cd6c6e23.html>. **Never delete
  it.** Search Console re-checks it and removing it drops ownership of the
  property. The property is a URL-prefix one, not a Domain property, because
  the Domain method needs a DNS record on `github.io`. Still to do by hand:
  submit `sitemap.xml`, request indexing for the root once, and optionally
  import the property into Bing Webmaster Tools. Expect weeks, not days, before
  a name query moves.
- **No X/Twitter link in the structured data.** The GitHub profile lists
  `OpenClawTech`, but X blocks automated checks so it could not be verified as
  Ben's, and it is a project handle rather than a personal one. Decide whether
  it belongs in `sameAs`.

## Editing notes

- `index.html` has three places that repeat the same description text: the
  `<meta name="description">`, the Open Graph tags, and the Twitter tags. Change
  one, change all three.
- Update `<lastmod>` in `sitemap.xml` and `dateModified` in the JSON-LD when the
  content meaningfully changes.
- The canonical URL is `https://benthompsondev.github.io/` with the trailing
  slash. Keep it that way.
- `robots.txt` here covers the whole `benthompsondev.github.io` origin, so it
  also applies to the project sites like `/cloakscan/` and `/wedding-50-50/`.
  Do not add a `Disallow` without checking what else it would block.
- Only add a `sameAs` entry to the structured data for a public URL that has
  actually been checked and clearly belongs to Ben.
