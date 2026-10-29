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
| `index.html` | The front page. Content, CSS, and the ProfilePage/Person structured data |
| `shared-mailbox-migration-readiness/index.html` | Case study: checking delegate readiness before migrating a shared mailbox during a phased Exchange hybrid migration. Self-contained like `index.html`, with its own TechArticle structured data pointing back at the Person `@id` |
| `robots.txt` | Allows crawling and points at the sitemap |
| `sitemap.xml` | The site root and indexable project pages on the same domain |
| `.nojekyll` | Skips Jekyll processing so Pages just serves the files |

## Open follow-ups

- **Keep the Google Search Console verification file.**
  `google0de73824cd6c6e23.html` sits in the repo root and serves at
  <https://benthompsondev.github.io/google0de73824cd6c6e23.html>. **Never delete
  it.** Search Console re-checks it and removing it drops ownership of the
  property. The verified property is the URL-prefix
  `https://benthompsondev.github.io/`, which also covers the project sites.
  Bing Webmaster Tools also has a verified property for this hostname. Check
  the current webmaster reports before submitting anything; a submission
  receipt is not proof of indexing.
  Do not repeatedly submit unchanged sitemaps or URLs.
- **The other project pages carry no structured data.** `/usageloop/` has
  `SoftwareApplication` and `Person` JSON-LD; `/cloakscan/` and
  `/ledger-local-finance/` have none. That is a fix in those repos, not this
  one, but it is the biggest remaining discovery gap on this origin.
- **No X/Twitter link in the structured data.** The GitHub profile lists
  `OpenClawTech`, but X blocks automated checks so it could not be verified as
  Ben's, and it is a project handle rather than a personal one. Decide whether
  it belongs in `sameAs`.

## Editing notes

- The host-root file with a 32-character hexadecimal name and `.txt` extension
  is the IndexNow ownership file. Its contents must match its filename. Keep
  it published while using IndexNow; it is not a tracking script. One root
  key covers this hostname and its project directories, not other `github.io`
  hosts. Submit only genuinely new, changed or deleted URLs. An accepted
  request confirms receipt, not indexing. See the
  [IndexNow protocol](https://www.indexnow.org/documentation).

- `index.html` has three places that repeat the same description text: the
  `<meta name="description">`, the Open Graph tags, and the Twitter tags. Change
  one, change all three.
- Update `<lastmod>` in `sitemap.xml` and `dateModified` in the JSON-LD when the
  content meaningfully changes. Base dates on the page's content revision,
  including the owning project repo for project pages. A Pages rebuild or an
  HTTP `Last-Modified` timestamp alone does not prove that the content changed.
  Leave `<lastmod>` out when the content date cannot be established.

  Google ignores `<changefreq>` and `<priority>`, so this sitemap does not carry
  them. Do not add them back.
- The canonical URL is `https://benthompsondev.github.io/` with the trailing
  slash. Keep it that way.
- `robots.txt` here covers the whole `benthompsondev.github.io` origin, so it
  also applies to the project sites like `/cloakscan/` and `/wedding-50-50/`.
  Do not add a `Disallow` without checking what else it would block.
- Only add a `sameAs` entry to the structured data for a public URL that has
  actually been checked and clearly belongs to Ben.
