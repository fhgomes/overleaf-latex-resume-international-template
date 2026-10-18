# Agent guide — LaTeX resume template

Read [README.md](README.md) before editing. This is an AltaCV-based LaTeX
template, built with pdfLaTeX; it is not a Node or Python application.

- Make content, layout and ATS changes in `main.tex`. Preserve the deliberate
  glyph mappings, icon suppression and keep-together macros documented there.
- Keep `altacv.cls` unchanged unless the task specifically requires a class
  change. Preserve AltaCV's LPPL attribution in
  [ALTACV-README.md](ALTACV-README.md) and the license split in
  [LICENSE](LICENSE).
- The example resume contains real, public information. Do not invent career
  facts or add private contact details. Keep English resume prose and the
  README's bilingual structure.

## Validation

With a local TeX distribution and `latexmk`, compile from this directory:

```bash
latexmk -pdf main.tex
```

This is the build documented in the README and used by
[CI](.github/workflows/build.yml), with shell escape disabled. Inspect the PDF
for overflow, page breaks and legible extracted text after layout changes.
If TeX tools are unavailable, state that compilation was not run; do not report
an unobserved CI result. There is no separate automated test suite.

Generated PDFs and TeX auxiliary files are build outputs. Tags matching `v*`
trigger publication of release assets; create tags or publish releases only
when requested.
