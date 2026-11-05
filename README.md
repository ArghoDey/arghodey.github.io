# Argho Dey - Academic Homepage

A lightweight, dependency-free academic site (plain HTML + one CSS file) hosted on
**GitHub Pages** at <https://arghodey.github.io/>. The layout follows
[Hyde](https://github.com/poole/hyde): a fixed dark sidebar for identity and navigation, one narrow
reading column for content.

## Structure

```
index.html          Home   - biography, selected publications, contact
publications.html   Publications - journal, conference and under-review papers
research.html       Research - statement, BEV perception and planning, collaborations
teaching.html       Teaching - assistantships, conferences and seminars
cv.html             CV     - education, appointments, awards, languages
papers/             One page per paper: authors, venue, links, abstract
figures/            Architecture diagrams used on the research page
style.css           Single stylesheet for every page
argho1.jpg          Portrait used in the sidebar
sitemap.xml         Every page, for search engines
robots.txt          Allows crawlers and points at the sitemap
```

## Search engines

Every page carries a title, a description, a canonical URL, Open Graph/Twitter tags, and JSON-LD
(`Person` on the home page, `ScholarlyArticle` with the DOI on each paper page). `sitemap.xml` lists
all 18 URLs and `robots.txt` points at it, so the site only needs to be submitted once in each search
console:

- Google Search Console: add `https://arghodey.github.io/`, verify with the HTML file it gives you
  (drop it in this folder), then submit `sitemap.xml`.
- Bing Webmaster Tools (also feeds DuckDuckGo): import from Google, submit `sitemap.xml`.
- Baidu 站长平台, for searches inside China: add the site, verify, submit `sitemap.xml`.

If a custom domain is added later, the canonical and `og:url` values (currently absolute and pointing
at `https://arghodey.github.io/`) have to be updated to match.

Every paper listed on `publications.html` links to its own page under `papers/`, which carries the
full author list, the venue and status, links to the paper and code where they exist, and the
abstract. Adding a paper means adding one file to `papers/` and one `<li>` to the matching list -
`Journal Articles`, `Conference Papers`, or `Under Review`.

## Publishing

The site is a user Pages site: the repository must be named `arghodey.github.io` and Pages must serve
the `main` branch from `/ (root)`.

1. Open `github.com/ArghoDey/arghodey.github.io` → **Add file → Upload files**.
2. Drag in every file, **including the `papers/` and `figures/` folders** (GitHub accepts folders by
   drag-and-drop). Overwrite on commit.
3. Commit to `main`, wait about a minute, then open <https://arghodey.github.io/>.

With git:

```bash
git clone https://github.com/ArghoDey/arghodey.github.io.git
cd arghodey.github.io
# replace the files with the ones from this folder
git add -A && git commit -m "Restructure site" && git push origin main
```

## Editing notes

- The sidebar block is repeated in every page (it is the template header). If you change the name,
  the affiliation line, the navigation or the contact links, change them everywhere - including the
  thirteen files in `papers/`, whose relative paths use a `../` prefix.
- Colours, fonts and the sidebar width live in the `:root` block and the `@media` blocks at the top of
  `style.css`. `--side-bg` is the sidebar colour, `--link` the link blue.
- Paper pages put the title in an `<h1>`, then authors, venue, links, an `<hr>`, and the abstract under
  an `<h2>`. Keep that order so all thirteen pages read the same way.
- Figures are downscaled exports from the papers. Keep them under about 2200 px wide.
- The CV page has a print stylesheet: printing it drops the sidebar and gives a clean paper copy.

## History

The first version of this site was a single-column warm-toned page describing Argho as a master's
student working on BEV perception. It has since been reorganised after the M.Sc. (Chongqing
University, 2026), the move to algorithm engineering at Beijing Lingyu Intelligent Technology, and the
move to doctoral study at the Department of Automation, Tsinghua University. A detailed doctoral research
plan was deliberately left off the public site.
