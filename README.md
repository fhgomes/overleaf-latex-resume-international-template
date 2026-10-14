# International LaTeX Resume Template (AltaCV, Overleaf-ready)

An international, ATS-friendly resume/CV template for software engineers and
other tech professionals, built on top of [AltaCV](https://github.com/liantze/AltaCV)
by LianTze Lim. The example content in `main.tex` is a real, public resume
(Fernando Gomes's — phone number removed) so you can see the full layout in
use, not a lorem-ipsum placeholder.

![Preview](https://github.com/fhgomes/overleaf-latex-resume-international-template/releases/latest/download/preview.png)

## Open in Overleaf

Click to open this template directly in Overleaf, pre-loaded and ready to compile:

[![Open In Overleaf](https://img.shields.io/badge/Open%20in-Overleaf-47A141?logo=overleaf&logoColor=white)](https://www.overleaf.com/docs?snip_uri=https://github.com/fhgomes/overleaf-latex-resume-international-template/releases/latest/download/overleaf-template.zip&engine=pdflatex)

```
https://www.overleaf.com/docs?snip_uri=https://github.com/fhgomes/overleaf-latex-resume-international-template/releases/latest/download/overleaf-template.zip&engine=pdflatex
```

This uses Overleaf's documented ["Open in Overleaf" API](https://www.overleaf.com/learn/how-to/Open_your_project_in_Overleaf):
`snip_uri` points at the `overleaf-template.zip` asset published with every
tagged release, and `engine=pdflatex` sets the compiler. If you aren't logged
in, Overleaf will ask you to sign in first and then open the project.

### Manual route (no "Open in Overleaf" link needed)

1. Go to this repo's [Releases](https://github.com/fhgomes/overleaf-latex-resume-international-template/releases/latest) page and download `overleaf-template.zip`.
2. In Overleaf: **New Project → Upload Project**, and upload the zip as-is (it is flat — `main.tex`, `altacv.cls`, `sample.bib` at the root, no extra folder).
3. In the Overleaf editor, open the **Menu** (top-left) and set **Compiler = pdfLaTeX**.
4. Compile.

### Use this as a GitHub template

This repository is a GitHub **template repository**. Click **"Use this
template"** (top of the repo page) to create your own copy under your account,
then edit `main.tex` with your own content.

## Local build

No Overleaf account needed if you have a local TeX installation
(TeX Live / MacTeX / MiKTeX) with `latexmk`:

```bash
latexmk -pdf main.tex
```

This repository also has no local TeX installation of its own — the CI
workflow (`.github/workflows/build.yml`) is what compiles `main.tex` on every
push/PR, and what builds and publishes the release assets on every `v*` tag.

## Bringing Overleaf edits back to GitHub (no paid plan needed)

Overleaf's GitHub sync is a paid feature, but you don't need it for a
one-person template like this one:

1. In Overleaf, open **Menu → Download → Source** to get a `.zip` of your
   current project.
2. Unzip it, and replace `main.tex` (and `altacv.cls`/`sample.bib` if you
   changed them — you normally shouldn't) in your local clone of this repo.
3. `git add`, `git commit`, `git push` as usual.

## What differs from stock AltaCV

This template keeps AltaCV's class (`altacv.cls`) untouched and makes all
customization in `main.tex`'s preamble:

- **ATS (Applicant Tracking System) readability**: ligature glyphs (`ff`,
  `fi`, `fl`, `ffi`, `ffl`) are mapped back to real letters in the PDF's text
  layer via `glyphtounicode` + `\pdfgentounicode=1`, and the FontAwesome
  icons next to e-mail/LinkedIn/location are stripped (`\AtBeginDocument`
  redefines them to empty) — some ATS parsers extract icon glyphs as
  corrupted characters right next to the contact text, which can break field
  extraction.
- **Keep-together guards**: `\jobguard` and `\sectionguard` (built on
  `needspace`) stop a job entry or section heading from being orphaned at
  the bottom of a page when the content is long enough to span multiple
  pages, which a one-page AltaCV normally doesn't need to worry about.
- **`\techline`**: a small helper that renders a "Technologies: ..." line
  inside a job's bullet list, visually secondary (smaller, tighter leading)
  to the main bullet points.
- **Blue palette and tighter spacing**: a custom color scheme
  (`DarkPastelRed`/`PastelRed` names are kept from AltaCV but recolored to
  blues), slightly tighter margins, and tighter bullet spacing
  (`itemsep`/`topsep`/`parsep`) to fit more content per page.

See the comments at the top of `main.tex` for the full rationale of each
custom macro and ATS tweak.

## International resume tips (brief)

This template defaults to conventions common outside Brazil/LatAm for an
English-language resume aimed at international (US/EU/remote) roles:

- Write in English; keep it ATS-readable (no tables for key facts, no text
  baked into images).
- No photo, age, marital status, or national ID numbers — common in
  Brazilian résumés, unusual and sometimes legally sensitive elsewhere.
- 2–3 pages is acceptable for a senior/staff profile with a long history;
  one page is not a hard rule outside entry-level roles.
- Quantify impact in bullets (%, $, scale, team size) rather than listing
  responsibilities.
- Keep contact info minimal: name, one professional link (LinkedIn/GitHub),
  e-mail, country/region. Phone number is optional — see the commented-out
  placeholder in `main.tex`.

## A note on Overleaf's template gallery

Overleaf's [public template gallery](https://www.overleaf.com/latex/templates)
does not accept CV/résumé templates for publication. That's why this
template is distributed as a GitHub repository (as a template repo, and via
the "Open in Overleaf" link above) instead of through the gallery.

## Credits & licenses

- **AltaCV** (`altacv.cls`) is by [LianTze Lim](https://github.com/liantze)
  and is licensed under the
  [LaTeX Project Public License (LPPL) 1.3c](https://www.latex-project.org/lppl.txt)
  or later. Its original README is kept, renamed, at
  [`ALTACV-README.md`](./ALTACV-README.md) for attribution.
- Everything else in this repository (this README, `main.tex`'s
  customizations, the CI workflow) is © Fernando Gomes and licensed under
  [MIT](./LICENSE).
- The example résumé content in `main.tex` is Fernando Gomes's real, public
  resume — reuse the **structure**, replace the **content** with your own.

---

## Português

Este é um template internacional de currículo em LaTeX (ATS-friendly),
baseado no [AltaCV](https://github.com/liantze/AltaCV). O conteúdo de exemplo
em `main.tex` é o currículo real e público de Fernando Gomes (telefone
removido), para servir de referência completa de layout.

- **Abrir no Overleaf em um clique**: use o botão/link "Open in Overleaf" no
  topo deste README.
- **Usar como template no GitHub**: clique em "Use this template" nesta
  página do repositório.
- **Build local**: `latexmk -pdf main.tex` (requer TeX Live/MacTeX/MiKTeX).
- **Trazer edições do Overleaf de volta pro GitHub** sem plano pago: Menu →
  Download → Source no Overleaf, substituir os arquivos localmente, e
  `git commit`/`git push`.
- Dicas de currículo internacional: inglês, sem foto/idade/estado civil, 2–3
  páginas são aceitáveis para perfis senior, bullets quantificados, e texto
  legível por ATS (nada de informação essencial só em imagem/tabela).
- O [AltaCV](https://github.com/liantze/AltaCV) é licenciado em LPPL 1.3c; o
  restante deste template é MIT. O conteúdo do currículo é de Fernando Gomes —
  reaproveite a estrutura, troque o conteúdo.
