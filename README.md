<div align="center">

<a href="https://www.lib.ncsu.edu/" aria-label="NC State University Libraries"><img src="site/images/lib_logo_whiteBG.svg" width="400" alt="NC State University Libraries logo" /></a>

<h2>Vibe Coding and the Practical Applications of Artificial Intelligence in Instructional Design and Educational Practice</h2>

<a href="https://www.lib.ncsu.edu/workshops"><img alt="NC State Libraries Workshops" src="https://img.shields.io/badge/NC%20State%20Libraries-Workshops-red"></a>
<a href="https://www.lib.ncsu.edu/staff/department/data-science-services"><img alt="Data Science Services" src="https://img.shields.io/badge/Data%20Science%20Services-Libraries-red"></a>
<a href="https://go.ncsu.edu/getdatahelp"><img alt="Get Data Help" src="https://img.shields.io/badge/Get%20Data%20Help-go.ncsu.edu%2Fgetdatahelp-red"></a>

</div>

A hands-on session from NC State University Libraries' Data Science Services for NC State's Instructional Design
Interest Group (IDIG), first taught on Zoom on November 24, 2026. Participants build a small practice activity,
"Measurable or Not?", in Gemini Canvas with their NC State account. They improve it one change at a time, test it, and
take it out of Canvas as a file. Then they watch an agentic coding tool turn the same activity into a version they
could put in a course, with editable content, automated keyboard tests, and packages for Storyline and an LMS. No
coding needed.

**Session guide:** <https://ncsu-libraries.github.io/ai-idig/> (short link: <https://go.ncsu.edu/ai-idig>)

## What's here

| Path | Contents |
| --- | --- |
| `site/index.qmd` | The guide: the whole session on one page, with the extra activities and the reference |
| `site/slides/index.qmd` | Seven slides for the start and the end: the go link, Data Science Services, the presenter and a quick poll, the evaluation |
| `site/_variables.yml` | Facts the page and the deck share: the date, the links, the dry-run times |
| `site/_starter-anatomy.md` | The starter prompt cut into its five PARTS, generated from the page |
| `site/images/` | Logos, the Data Science Services slides, the QR code and screenshots |
| `site/theme/` | The NC State theme for the page and the deck |
| `tools/` | Quarto in Docker, a link checker, a screenshot tool, a slide overlap checker, the prompt extractor |

## Build it locally

The scripts run Quarto 1.10.18 in Docker, so start Docker first.

```bash
python3 tools/extract_prompts.py  # after changing a prompt on the page
tools/quarto.sh render site      # builds site/_site
tools/quarto.sh preview site     # or serve it at http://localhost:4848 while editing
python3 tools/check_links.py     # checks every link and image in site/_site
```

## Publishing

Pushing to `main` runs `.github/workflows/deploy-pages.yml`, which renders the site and deploys it to GitHub Pages. Set
**Settings → Pages → Source** to **GitHub Actions** *before* the first push. The first push of a root commit doesn't
trigger the paths-filtered workflow, so run it once from the **Actions** tab.

## License

Content is licensed [CC BY 4.0](LICENSE-CC-BY-4.0.md) and code is [MIT](LICENSE).
