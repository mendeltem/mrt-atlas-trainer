# MRI Atlas Trainer

A free, interactive tool for learning **neuroanatomy** — explore real MRI slices and test yourself with a quiz. Bilingual (DE/EN), runs entirely offline in the browser, no installation.

**Live demo:** https://mendeltem.github.io/mrt-atlas-trainer/

---

## What is it?

A tool to learn brain anatomy and the common atlas regions in a hands-on way —
made for students and anyone getting started with brain MRI.

## Features

- **Explore:** click a region → instantly see its name + function
- **Quiz:** self-test with instant feedback and a score
- **Two atlases:** AAL and Harvard-Oxford, each rendered on its matching MNI152 template
- **Bilingual:** switch between German and English
- **Offline & instant:** everything in a single HTML file — no server, no install
- **Mobile-friendly**

## How it works (in short)

The FSL atlases (AAL, Harvard-Oxford) are pre-rendered to images on the MNI152
standard brain using Python. Alongside the display image there is a **lossless
label map** (pixel value = region ID); a click reads the ID and translates it
into the region name — deterministic, no ML. Everything is embedded as Base64
into a single HTML file.

## Self-hosting

It's a single static file — just serve `index.html` on any static host
(e.g. GitHub Pages, Netlify, or Cloudflare Pages).

## License

- **Code:** MIT — see [LICENSE](LICENSE).
- **Data (atlases & MRI templates):** their own licenses, partly
  **non-commercial only** (FSL/Harvard-Oxford, AAL). Details and citations in
  [THIRD-PARTY.md](THIRD-PARTY.md).

> Please use **free of charge and non-commercially** (no ads, no paywall,
> no resale) and keep the source attributions.

## Author

**Uchralt Temuulen** · Data Scientist, Charité – Universitätsmedizin Berlin

LinkedIn: https://www.linkedin.com/in/YOUR-PROFILE/

Feedback and suggestions are welcome!
