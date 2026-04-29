# AI · AGENCY — Research Project Website

A static, downloadable, soft-codable site for the research project **AI Use and Human Agency in Graduate Education** by Vladimír Šucha and Antoine Cerqueira Da Costa, conducted at the European University Institute, School of Transnational Governance.

---

## Folder structure

```
site/
├── index.html              # Home
├── information.html        # Information (what participation involves)
├── methodology.html        # Methodology (high-level only)
├── data-handling.html      # Data handling & rights
├── about.html              # Researchers (with LinkedIn links)
├── contact.html            # Contact + #interested sign-up form
├── css/
│   └── style.css           # Single shared stylesheet
├── js/
│   └── script.js           # Vanilla JS, no dependencies
└── assets/
    ├── Privacy-Statement-Consent-Form.pdf
    └── Data-Notification-Form.pdf
```

To preview: open `index.html` in any browser, or serve the folder with `python3 -m http.server` and visit `http://localhost:8000`.

---

## 1 · Sitemap

```
[ 01 ] Home  (index.html)
   ├─ Hero · "A study on the quiet shift in how we think"
   ├─ The research question
   ├─ Pull quote
   ├─ The study at a glance (4 stat strip)
   ├─ How it unfolds (3-phase timeline)
   └─ Participate CTA → /contact.html#interested

[ 02 ] Information  (information.html)
   ├─ Page hero
   ├─ Who can participate
   ├─ Time commitment (4 stat strip)
   ├─ What it looks like (4-phase timeline)
   ├─ What we ask
   ├─ FAQ (7 disclosures)
   └─ Sign-up CTA

[ 03 ] Methodology  (methodology.html)
   ├─ Page hero
   ├─ Note on intentional brevity (anti-priming notice)
   ├─ Approach (mixed-methods)
   ├─ Three modules
   ├─ Tools & analysis (Qualtrics, aTrain, local Mistral 2B)
   └─ Document downloads

[ 04 ] Data Handling  (data-handling.html)
   ├─ Page hero
   ├─ Pseudonymisation (PIC system)
   ├─ Pull quote
   ├─ Where data lives
   ├─ Retention (3-tier schedule)
   ├─ Your rights (4 enumerated)
   └─ Document downloads

[ 05 ] About  (about.html)
   ├─ Page hero
   ├─ Researcher cards × 2 (Šucha · Cerqueira)
   │     each with LinkedIn link & EUI affiliation
   └─ Affiliation block

[ 06 ] Contact  (contact.html)
   ├─ Page hero
   ├─ Direct emails (vladimir.sucha@eui.eu · antoine.cerqueira@eui.eu)
   ├─ DPO & Ethics Committee contact lines
   └─ #interested form (name · email · optional note · consent checkbox)
```

---

## 2 · Three Hero Layout Variations

The implemented hero is **Variation A**. Variations B and C are alternative directions you can swap in by replacing the `.hero` block in `index.html`. Each lives within the same Ember & Onyx aesthetic.

### Variation A — *The Stairway* (currently live)

A vertical composition. A glowing aperture at the top of the frame; perspective lines suggesting a staircase converging upward; a small silhouette walking toward the light. Headline left, condensed editorial card on the right with a bracketed `(participate)` CTA. Page numerals top-left, EUI affiliation top-right. **Mood:** ascent, focus, the feeling of leaning into a question.

### Variation B — *The Threshold*

Full-bleed horizontal arch motif: an amber-lit doorway centred on a charcoal field, with mist curling at the base. Title set across two lines beneath the arch in extra-large display serif. CTA appears as a lone bracketed line `(enter the study)` in the lower-left. **Mood:** invitation, threshold, choosing to step in. Useful when you want the page to feel quieter and more contemplative.

### Variation C — *Split Editorial*

A magazine-cover split. Left two-thirds: large display serif with a pull-quote-style sentence ("*Where does your thinking end, and the model's begin?*"). Right one-third: a tall vertical photographic panel (or atmospheric gradient) showing a figure mid-thought against an ember backdrop, with metadata (`STUDY 01 · 2026 · EUI`) running vertically alongside. **Mood:** literary, declarative, designed for the page to read like an issue cover. Good for press or share-card contexts.

> All three keep: the bracketed `[menu]` button, page numerals (`01 / 06`), serif/sans contrast, and the same scroll story below.

---

## 3 · High-Conversion Copy — PAS Framework

These blocks are written in the **Problem → Agitation → Solution** structure and can be used on the home page or in outreach material (emails, induction-session intros, social cards). The current home page draws on these but uses a softer editorial register; below is the more conversion-pointed version for use in recruitment outreach.

### Problem
> Most graduate students now use AI tools every day — to draft, summarise, structure, brainstorm. The change has been fast, and quietly absorbed.

### Agitation
> Faster than we've had time to ask: where does *your* thinking end, and the model's begin? Are you using a tool, or learning to think with one looking over your shoulder? Most people don't know. Most don't have a structured way to find out.

### Solution
> This study gives you that structure. Ten weeks of short, weekly self-documentation — fifteen minutes — and three quiet conversations. Pseudonymised by design. No grading, no judgement, no extraction. Just an honest occasion to notice your own working habits before they finish settling.
>
> *Sign up. The study begins this term.*

---

## 4 · Design system at a glance

| Token | Value |
|---|---|
| Onyx (background) | `#08070a` |
| Onyx soft | `#15110f` |
| Ember core | `#ff6a1a` |
| Ember glow | `#ff8c3f` |
| Ember soft | `#ffb478` |
| Paper (text) | `#f4ede2` |
| Paper mute | `#c9bfb1` |
| Paper dim | `#8a8275` |
| Display serif | Cormorant Garamond (300/400/500, italics) |
| UI / body sans | DM Sans (300/400/500) |
| Max width | 1440 px (1680 at 1920+, 1920 at 2560+) |
| Gutter | `clamp(20px, 4vw, 48px)` |
| Section padding | `clamp(80px, 12vw, 160px)` |

All colours and type are exposed as CSS custom properties in `:root` for easy global re-skinning.

---

## 5 · Responsive breakpoints (Automated Breakpoint Logic)

| Width | Behaviour |
|---|---|
| ≤ 720 px (foldables, phones) | Single-column hero, stacked stat strip (2×2), single-column phases, single-column docs |
| 721–880 px (small tablets) | Mixed: split layouts collapse, mobile menu still active |
| 881–1439 px | Desktop layout, full multi-column grids |
| 1440–1919 px | Container caps at 1440 px |
| 1920–2559 px | Container at 1680 px, body 17 px |
| ≥ 2560 px (4K) | Container at 1920 px, body 18 px |

Mobile navigation transitions into a full-screen, large-serif `[menu]` overlay with text-labelled close button — preserving the bracketed editorial syntax across viewports.

---

## 6 · Accessibility & SEO

- Semantic landmarks: `<header>`, `<nav>`, `<main>` content via `<section>`, `<footer>`.
- All decorative gradients/silhouettes carry `aria-hidden="true"`.
- Form fields have explicit `<label>` associations and `required` attributes; the consent checkbox is labelled and linked to the privacy PDF.
- `prefers-reduced-motion: reduce` disables transitions, animations, and reveal-on-scroll.
- Keyboard: `Esc` closes the mobile menu; focus styles inherit from default browser unless soft-coded.
- `Schema.org/ResearchProject` structured data is embedded on the home page (extend to other pages as needed).
- Meta `description` and `og:` tags populated per page.
- Images: the hero uses CSS-generated atmosphere rather than raster files, so there is no image alt-text to maintain. If you replace the gradient stage with photography, set `alt` to *empty* (`alt=""`) for purely decorative images and a short descriptive string for content-bearing images.

---

## 7 · Soft-coding hand-off notes

**Wiring the interest form.** The form (`#interest-form`) currently logs submissions to the console and shows a success message. Replace the `console.log` line in `js/script.js` with a `fetch()` to your handler (Formspree, Qualtrics intake, EUI internal endpoint, etc.):

```js
fetch('/api/interest', {
  method: 'POST',
  body: data,
  headers: { 'Accept': 'application/json' }
}).then(r => r.ok && document.querySelector('#interest-success').classList.add('is-shown'));
```

**Replacing the hero atmosphere.** The home page hero is built entirely in CSS for portability. To swap in a video/Lottie/photography placeholder, replace `.hero-stage`, `.hero-figure`, and `.hero-fade` with your own element. The text grid (`.hero-content`) sits at `z-index: 3` and overlays anything beneath.

**Adding pages.** Copy any inner page (e.g. `methodology.html`), update `<title>`, `<meta name="description">`, the `.page-hero` content, the page numeral in `.eyebrow .pg-num`, and add a corresponding entry to the desktop and mobile `<nav>` of every page.

**Updating contact emails.** The lead-author email `vladimir.sucha@eui.eu` appears on `index.html`, `information.html`, `methodology.html`, `data-handling.html`, `about.html`, `contact.html`, and the footer of every page. Use a global find-and-replace if the address ever changes.

**Placeholders to swap in production:**
- `[ Lottie placeholder ]` — none required; the hero atmosphere is CSS-only. If you want a Lottie, drop it inside `.hero-stage` with `position:absolute; inset:0; z-index:0;`.
- `[ Video background placeholder ]` — `<video autoplay muted loop playsinline>` inside `.hero-stage`, with `object-fit: cover` and the existing `.hero-fade` left in place to preserve text legibility.
- Photographic portraits can replace the silhouette inside `.person .frame` — use 4:5 portrait crop, monochrome, with warm shadows to stay aesthetically aligned.

---

## 8 · Document downloads

| File | Source PDF | Path |
|---|---|---|
| Privacy Statement & Consent Form | `UPDATED_AI_RP_-_Privacy_statement_+_consent_form_-_SUCHA_+_CERQUEIRA.pdf` | `assets/Privacy-Statement-Consent-Form.pdf` |
| Data Notification Form | `UPDATED_AI_RP_-_DATA_NF_Surveys_-_SUCHA_+_CERQUEIRA.pdf` | `assets/Data-Notification-Form.pdf` |

Both documents are linked from the Methodology page, the Data Handling page, the Contact form's consent line, and every footer.

---

*Built for soft-coding. Strip what you don't need. The bones are deliberately simple.*
