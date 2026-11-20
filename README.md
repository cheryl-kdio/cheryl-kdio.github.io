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

- `index.qmd` contains the editorial selection. Update its featured article, selected writings and research highlight when the selection changes. The measured rates chart in `files/images/market-rates-by-maturity.png` comes from the existing yield-curve calibration project.
- `posts.qmd` is the Writings archive, with Quarto search, category filters and RSS. `research.qmd` curates existing studies and links to the reports, publications and applications in `publications.qmd`.
- `topics.qmd` groups articles and projects by theme. The linked `browse/` indexes automatically list articles from their folders, and their scoped sidebars are configured in `_quarto.yml` and assigned in each folder’s `_metadata.yml`.
- Set `title` and `categories` in article metadata. Preserve coursework categories (`ensai-gdr`, `m2mo`) and document `aliases` for older URLs.
- Use short, descriptive lowercase filenames. Keep each article’s data and figures near its source. `_freeze/` contains cached computations and `docs/` contains generated output. Make editorial changes in the source files.
- Use fenced Div classes `.definition`, `.theorem`, `.proposition`, `.lemma`, `.proof`, `.remark`, `.example` or `.mathematical-intuition` for scientific blocks. Include the block title in the source. Quarto remains responsible for MathJax, citations and cross-references.

## Local preview and build

```sh
quarto preview --output-dir _site
quarto render
```

To inspect layout without executing Python or R code:

```sh
quarto render --no-execute
```
