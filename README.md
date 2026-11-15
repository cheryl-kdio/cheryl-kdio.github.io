# Personal academic website

Quarto website. Source pages are organised by subject; ENSAI and M2MO remain article categories rather than folders.

## Content map

```text
posts/
  finance/
    derivatives/               # Markets, no-arbitrage and pricing
      numerical-methods/       # PDE methods for options
    interest-rates/            # Instruments, yield curves and Vasicek
    volatility/                # Stochastic local volatility notebook
    portfolio-management/      # Markowitz and portfolio construction
      practical-work/          # Market, liquidity and bond valuation risks
    risk-management/
      value-at-risk/           # VaR, extreme values, GARCH and copulas
    model-calibration/         # Black-Scholes, Heston, filtering and curve calibration
    financial-analysis/        # Financial statements and prudential regulation
    sustainable-finance/
  statistics/
    machine-learning/          # Penalised regression, SVM, boosting, feature selection
    dependence/                # Pearson and Spearman correlations
glossary/
  finance/
  mathematics/
notes/                         # Practical and miscellaneous notes
files/                         # Shared images, CV and includes
```

## Navigation and adding content

- `topics.qmd` displays topic and subtopic navigation cards. The linked `browse/` pages automatically list articles from their folders; `posts.qmd` provides the chronological listing and category filters.
- The sidebar is generated automatically from `posts/` and `glossary/`, including nested folders. New articles and subfolders appear after `quarto render` or during `quarto preview`; no manual article registration in `_quarto.yml` or `topics.qmd` is needed. A new top-level topic on the directory page needs a heading and folder-based listing in `topics.qmd` once; articles within that topic are discovered automatically.
- Article labels use their `title` metadata. Folder names become section labels (hyphens become spaces). Optional numeric `order` metadata controls navigation order.
- Use descriptive filenames in lowercase with hyphens. Keep article-specific data and images near their documents.
- Set `title` and `categories` in each article’s YAML header. Keep provenance categories (`ensai-gdr`, `m2mo`) and add subject categories such as `derivatives` or `pricing`; these automatically become listing filters.
- Moved documents carry `aliases` for their previous HTML addresses. Preserve these aliases.
- `_freeze/` contains cached computations; `docs/` contains generated output. Edit source files rather than generated HTML.

## Local preview and build

```sh
quarto preview
quarto render
```

To inspect layout without executing Python or R code:

```sh
quarto render --no-execute
```

## Scoped topic navigation

The home page links to `browse/<topic>/index.qmd` and its subtopic pages.
Each page discovers articles from the corresponding source folder and excludes drafts.
`_quarto.yml` defines scoped sidebars; `_metadata.yml` in each article subtopic assigns
its sidebar to existing and future articles automatically. Main topic pages show all
subtopics; subtopic pages and their articles show only their own branch.
New articles require no navigation changes. A new topic needs a browse page,
sidebar configuration, home link and folder metadata once.
