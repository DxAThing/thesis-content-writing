# LaTeX Engineering Conventions

## Purpose

Standard LaTeX formatting rules for research papers.
Load this reference when the user is working with LaTeX source files.

## Table Rules

### Hard Rules (booktabs style)
1. Put caption **above** the table.
2. Avoid vertical lines (`|`) in tabular columns.
3. Do not use double rules or dense `\hline` stacks.
4. Use `booktabs` style: `\toprule`, `\midrule`, `\bottomrule`.
5. Use as few horizontal rules as possible; lines separate groups, not every row.
6. Highlight key numbers with subtle color emphasis (do not overcolor).

### Readability Rules
1. Label metric direction in column headers: `PSNR ↑`, `LPIPS ↓`.
2. Add units when needed.
3. Align text columns left; numeric columns consistently.
4. Keep numeric precision consistent within a metric column.
5. Group multi-dataset results using `\multicolumn` + `\cmidrule`, not vertical separators.
6. One table, one message: do not mix unrelated results.
7. Keep caption focused on setting/protocol/notation, not long discussion.

### Minimal LaTeX Checklist
1. Preamble: `\usepackage{booktabs}`, `\usepackage{colortbl,xcolor}`, optionally `\usepackage{siunitx}`.
2. Replace `\hline`-heavy style with `\toprule/\midrule/\bottomrule`.
3. Put `\caption{...}` before `\label{...}` and keep caption above.
4. Use restrained highlighting; never color too many cells.

## Figure Rules

1. Use vector formats (PDF/SVG) for diagrams; raster (PNG) only for photos/screenshots.
2. Ensure all text in figures is readable at the final print size.
3. Use consistent color scheme across all figures.
4. Caption should summarize what the figure shows, not restate the method.
5. Place `\caption` and `\label` after `\includegraphics`.

## Formula Rules

1. Number all important equations that are referenced elsewhere.
2. Use `\eqref{}` for equation references (produces parenthesized numbers).
3. Define every symbol at first use.
4. Keep notation consistent with the surrounding text.
5. For inline math, avoid overly tall expressions that break line spacing.

## Recommended Packages

| Purpose | Package |
|---------|---------|
| Tables | `booktabs`, `multirow`, `makecell` |
| Colors | `xcolor`, `colortbl` |
| Figures | `graphicx`, `subcaption` |
| Math | `amsmath`, `amssymb`, `mathtools` |
| Algorithms | `algorithm2e` or `algorithmicx` |
| Hyperlinks | `hyperref` (load last) |
| Units | `siunitx` |
| Code listings | `listings` or `minted` |
