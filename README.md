# Index

A searchable index of every public repository on my GitHub — live at
**https://eeman1113.github.io/Index/**

The page pulls the repo list from the GitHub API at load time and merges it with
`decp.csv`, a curated data file. Descriptions in that file are written from the
actual code in each repo rather than from the repo blurb, so projects whose
README said "ascii" or "sotthing the mind" get a real explanation.

## `decp.csv`

One row per public repo, newest push first.

| Column | What it holds |
|---|---|
| `Repo Name` | Repository name (joins to the GitHub API result) |
| `Description` | What the project actually is, read off the source |
| `Topics` | Subject-matter keywords |
| `Tags` | Real tech stack — frameworks, libraries, APIs |
| `Domain` | The field it sits in, e.g. `Game Dev`, `AI Multi-agent / Research` |
| `Type` | `original`, `fork`, or `fork (modified)` |
| `Forked From` | Upstream `owner/repo`, for forks |
| `My Changes` | For modified forks: what I actually changed, with diff stats |
| `Live URL` | Deployed site, where there is one |

Forks are included because several carry real work of mine — a REST API crate
added to Harper, English i18n contributed to MiroFish, a multi-layer perceptron
merged into TheAlgorithms/Python. Each one's `My Changes` column records the
diff, and forks I only read are marked plainly as unmodified so nothing claims
credit it hasn't earned.

Private repositories are deliberately not listed here.

## Running it locally

The page fetches `decp.csv` over HTTP, so it needs a server rather than
`file://`:

```sh
python3 -m http.server 8000
# then open http://localhost:8000/
```
