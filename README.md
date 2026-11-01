# MRI Atlas Trainer

A free, interactive tool for learning **neuroanatomy** — explore real MRI slices and test yourself with a configurable quiz at **three difficulty levels**. Bilingual (EN/DE), runs entirely offline in the browser, no installation.

**Live demo:** https://mendeltem.github.io/mrt-atlas-trainer/

![MRI Atlas Trainer – quiz mode showing an axial MNI152 slice (AAL atlas, slice 17/32, z = 13 mm) with colored region overlays. A crosshair marks one structure and the side panel asks which region it highlights, offering multiple-choice answers, with a running right/wrong/remaining score.](mri_train_1.png)

---

## What is it?

A tool to learn brain anatomy and the common atlas regions in a hands-on way —
made for students and anyone getting started with brain MRI. You pick the level
of detail that matches where you are, from school biology up to clinical
neuropsychology.

## Features

- **Three difficulty levels** that scale the anatomical granularity to your background:
  - **Easy** – regions are grouped into 9 anatomical clusters (the four lobes,
    insula, limbic system, basal ganglia, thalamus, brainstem & cerebellum). The
    overlay is **recolored by cluster**, so the whole occipital lobe is one color,
    all frontal areas another, and so on — clean and uncluttered.
  - **Medium** – all named regions, but **left/right merged** (e.g. "Thalamus"
    instead of "Thalamus (left)"). Full per-region atlas colors. Both the
    "identify" and the "function" quiz are available.
  - **Hard** – every individual, side-specific region, full original behavior.
- **Explore:** click a region → instantly see its name + function (adapts to the level)
- **Configurable quiz:** a settings panel sits at the top of the quiz with
  sensible defaults already selected — just start, or change any option to
  restart the round with new settings. See [The quiz](#the-quiz) below.
- **Collect & study:** every region you click lands in your personal collection;
  **Study** turns it into flashcards and multiple-choice tests on what each region
  does. See [Study mode](#study-mode) below.
- **Two atlases:** AAL and Harvard-Oxford, each rendered on its matching MNI152 template
- **Bilingual:** English by default, switch to German anytime
- **Offline & instant:** everything in a single HTML file — no server, no install
- **Mobile-friendly**

## The quiz

The quiz is built around **mastery learning with explanatory feedback** rather
than a one-pass score. You configure it from a small panel of pre-toggled
options, and every answer teaches something — whether right or wrong.

**Settings (pre-selected defaults, change to restart):**

- **Question type** – *Anatomy* (identify the marked region), *Function* (which
  region performs a given role), or *Mixed* (both interleaved, each question
  keeping its own type). Function is unavailable in Easy mode.
- **Difficulty** – Easy / Medium / Hard, kept in sync with the header.
- **Count** – *Auto* (scales with mode & level: 12 / 16 / 18 / 20) or a fixed
  10 / 15 / 20.
- **Help** – hints on or off (off hides the hint button for a stricter run; the
  post-answer explanation stays either way).

**During the quiz:**

- **Mastery loop** – a wrong answer goes back into the queue and returns later,
  so the round ends only once every region is mastered. The "remaining" count
  reflects regions you haven't gotten yet, not just questions left.
- **Explanatory feedback** – after each answer you see the region's name and its
  function, then advance at your own pace with **Next** (no auto-skip).
- **Diagnostic near-miss feedback** – on a wrong answer the trainer recognizes
  *what kind* of mix-up it was and says so: the right region but the wrong
  **side (L/R)**, the **same lobe** but a different region, or a
  **functionally related** area. It stays silent when the mistake isn't
  instructive, instead of forcing a hint.
- **Progressive hints** – first a text hint (which lobe / what the region does),
  then the colored overlay as a reveal — instead of a single colour toggle.
- **Streaks & scoring** – a streak counter with milestone messages, and a final
  score based on **first-try accuracy** plus your best streak.

## Study mode

Learn what the regions *do*, using exactly the regions you picked yourself.

1. **Collect** – click through the MRI in *Explore*. Every region lands in
   *My collection* (left/right merged, so "Hippocampus" is one card). Uncheck
   *Collect clicks* to look around without collecting, or use the star on the
   region card and the × on each entry to curate the list. *All regions of this
   atlas* fills the collection in one go.
2. **Study** – pick a format and what to ask for:
   - **Flashcards** – recall the answer, flip the card, rate yourself
     (*Again* / *Knew it*).
   - **Multiple choice** – four answers, e.g. *Hippocampus → "Forms new memories
     and supports spatial navigation"*.
   - **Ask for** – *Function* (region → what it does), *Region* (function → which
     region), or *Mixed*.
3. **Master it** – a wrong answer comes back soon, and the round ends once every
   card is mastered. Afterwards you can practise only your mistakes. Each answer
   shows the region's function and a short anatomy/clinical note, and the crosshair
   marks the spot you clicked on the MRI.

**Difficulty** picks the wrong answers in multiple choice: *Easy* draws them from
other brain areas, *Hard* from the same area, so you have to tell neighbours apart.
Weak cards come first, and a ✓ marks cards you got right three times in a row.

Your collection and progress are saved in this browser only (`localStorage`);
nothing is sent anywhere. Works by touch on phones (compact MRI above the card,
*Study* bar at the bottom while collecting) and by keyboard on desktop (*Space*,
*1–4*).

## Difficulty levels & didactic mapping

The three levels mirror the progression of anatomical detail found across German
teaching curricula and standard textbooks, so each tier can be cited:

| Level  | Granularity                                   | Typical context                          | Reference |
|--------|-----------------------------------------------|------------------------------------------|-----------|
| Easy   | Lobes + major subcortical groups (9 clusters) | School / intro biology (Abitur)          | Rahmenlehrplan gymnasiale Oberstufe Biologie, LISUM Berlin-Brandenburg (2021); Campbell Biologie (Pearson) |
| Medium | Named gyri/regions, left/right merged         | Biopsychology (psychology degree)        | Pinel, Barnes, Pauli & Gamer, *Biopsychologie*, 11th ed. (Pearson 2024, ISBN 978-3-86894-442-6) |
| Hard   | Fine, lateralized regions                     | Clinical neuropsychology (medicine)      | Karnath & Thier (eds.), *Kognitive Neurowissenschaften*, 3rd ed. (Springer 2012, ISBN 978-3-642-25526-7); Hartje & Poeck, *Klinische Neuropsychologie*, 6th ed. (Thieme 2006) |

The clustering follows textbook convention: **basal ganglia** (striatum =
caudate + putamen, pallidum, plus the nucleus accumbens / ventral striatum in
Harvard-Oxford) and the **thalamus** are kept as separate clusters rather than
lumped together, since the thalamus belongs to the diencephalon.

## How it works (in short)

The FSL atlases (AAL, Harvard-Oxford) are pre-rendered to images on the MNI152
standard brain using Python. Alongside the display image there is a **lossless
label map** (pixel value = region ID); a click reads the ID and translates it
into the region name — deterministic, no ML. In Easy mode the same label IDs are
mapped to cluster colors on the fly; in Medium mode region names are stripped of
their side suffix. Everything is embedded as Base64 into a single HTML file.

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

LinkedIn: www.linkedin.com/in/uchralt-temuulen-31a3a570

Feedback and suggestions are welcome!
