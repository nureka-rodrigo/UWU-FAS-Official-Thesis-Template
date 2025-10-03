# UWU Thesis Template

Official dissertation template for the Faculty of Applied Sciences, Uva Wellassa University of Sri Lanka. The project supplies ready-to-edit chapters, preliminary pages, bibliography management, and glossaries so students can focus on content while remaining compliant with formatting requirements.

## Repository layout

| Path                 | Purpose                                                                                                                                                                                  |
| -------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `main.tex`           | Root document that compiles the entire thesis. Controls packages, front matter order, and bibliography style.                                                                            |
| `preliminary_pages/` | Title page, declaration, abstract, acknowledgements, abbreviations, and appendices placeholders with guidance text.                                                                      |
| `chapters/`          | Five fixed chapters (Introduction, Literature Review, Methodology, Results and Discussion, Conclusions and Recommendations) each populated with scaffolded subsections and writing tips. |
| `figures/`           | Store illustrations referenced in the thesis. Replace `Figure.png` with project-specific assets.                                                                                         |
| `references.bib`     | BibTeX database for citations.                                                                                                                                                           |
| `additional_doc/` | Additional documents for quick reference during writing. |

## Build instructions

1. Install a full LaTeX distribution (TeX Live, MiKTeX, or MacTeX) with the `glossaries`, `natbib`, and `mathptmx` packages.
2. From the repository root run the following sequence:

```powershell
pdflatex main.tex
makeglossaries main
bibtex main
pdflatex main.tex
pdflatex main.tex
```

`latexmk -pdf main.tex` is an alternative that automates the same cycle. Always re-run `makeglossaries` after changing abbreviations.

## Writing guidance highlights

- **Chapters 1–5** already include structured subsections, exemplar tables/figures, and reminders on citation practices. Replace the instructional prose with your own content while keeping the headings unless expressly advised by your supervisor.
- **Figures and tables**: follow the embedded samples for placing captions, labels, and cross references (e.g., `fig:overview}`, `tab:evaluation`). Use vector formats where possible and mention every figure/table in the surrounding text.
- **Citations**: manage sources in `references.bib` and cite them with `\citep` or `\citet`. The Harvard `agsm` style is pre-configured.
- **Abbreviations**: register each term in `preliminary_pages/abbreviations.tex` with `\newacronym` and refer to it in the body using `\gls`. Remember to rebuild glossaries.
- **Appendices**: leverage `preliminary_pages/appendices.tex` to introduce supplementary material; create additional appendix files as needed and include them via `\input` statements.

## Customisation checklist

- Update the title page with your dissertation title, author name(s), degree, and year.
- Replace placeholder guidance text chapter by chapter, ensuring the logical flow described in the template is preserved.
- Add or remove lots-of-content sections (`\listoftables`, `\listoffigures`, abbreviations) in `main.tex` depending on the presence of tables, figures, or acronyms.
- Store media assets in `figures/` and update paths in the figure environments.
- Extend the bibliography by editing `references.bib`; run the build sequence afterward to refresh citations.

## Support

For faculty-specific clarifications, consult your supervisor or the department’s formatting handbook. Contributions that improve the template or automate workflows are welcome via pull requests.
