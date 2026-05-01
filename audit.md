# LaTeX Report Audit

I ignored explicit TODO placeholders and obviously unfinished cells. Everything below is about material that reads as if it is meant to be final.

## Findings

12. **The layout strategy is brute force rather than proper LaTeX.** Representative examples in `chapters/planning.tex:18-45`, `chapters/process.tex:103-117`, `:225-255`, `:511-531`, `chapters/design_low.tex:166-179`, and `chapters/software.tex:137-162` lean heavily on `[H]` and `\resizebox{\textwidth}{!}` to pin and squash tables. The compile log is full of overfull/underfull boxes, and there is even an overfull `\vbox` around the Sprint 4 state-machine page. The document is fighting the typesetter instead of using it.

## Compile Notes

I compiled the report with `pdflatex` into `/private/tmp`. It builds, but not cleanly:

- Duplicate page-anchor warning from the front matter.
- Large numbers of underfull/overfull boxes across table-heavy sections.
- At least one overfull `\vbox` during the Sprint 4 state-machine page.

So yes, it technically compiles. No, that is not the same thing as being well put together.
