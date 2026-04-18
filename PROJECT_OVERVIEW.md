# Abilar Evidence Website — Project Overview

## Summary

A static multi-page website presenting clinical and veterinary evidence for Abilar wound balm.
Built as a proof of concept, closely following the design language of [abilar.com](https://abilar.com/en-fi).

---

## File Structure

```
RepolarProject/
├── index.html              # Entry page — two circle buttons
├── abilar.html             # Abilar (human) — global presence map + 4 indication cards
├── abilar-vet.html         # Abilar Vet — 2 veterinary study cards
├── diabetic-ulcer.html     # Detail page: Diabetic Ulcer  ← most developed
├── pressure-ulcer.html     # Detail page: Pressure Ulcer
├── leg-ulcer.html          # Detail page: Leg Ulcer
├── surgical-wound.html     # Detail page: Surgical Wound
├── styles.css              # Shared stylesheet (all pages) — currently v=8
├── PROJECT_OVERVIEW.md     # This file
└── assets/
    ├── diabetic-ulcer-study.pdf     # Downloadable clinical study PDF (Diabetic)
    ├── diabetic-study-cover.png     # Journal cover image (flip card back)
    ├── diabetic-case-1.png          # Case 1 clinical photo
    ├── diabetic-case-2.png          # Case 2 clinical photo
    ├── diabetic-case-3.png          # Case 3 clinical photo
    ├── diabetic-case-4.png          # Case 4 clinical photo
    └── expert-jokinen.png           # Dr. Janne Jokinen portrait photo
```

---

## Pages

### Page 1 — Entry (`index.html`)
- **Hero top section**: Forest background image sourced from abilar.com CDN with dark green gradient overlay
- **Hero bottom section**: Light off-white background with two large circle buttons
- **Circle buttons**:
  - `Abilar` (solid sage green) → links to `abilar.html`
  - `Abilar Vet` (white/outlined) → links to `abilar-vet.html`
- Staggered fade-in animation on page load

---

### Page 2 — Abilar Evidence (`abilar.html`)

#### Global Presence Map *(added in Session 2)*
- Full-width card with dark green header: **"Global Presence"**
- Interactive SVG world map powered by **amCharts 5** (CDN, no install)
- Highlighted countries (dark green `#38473a`): Finland, Sweden, Norway, Denmark, Germany, Poland, Greece, United Kingdom, Peru, Chile
- Excluded countries from initial list: Iceland, China (removed in Session 2)
- Added: Peru, Chile (South America — added in Session 2)
- Hover state on highlighted countries: slightly lighter green `#4a5e4c`
- Country tags displayed as pill badges below the map
- Map projection: Natural Earth 1 (no rotation, no zoom/pan)

#### Indication Cards (2×2 grid)
- Each card shows: indication number tag, indication name, study count meta
- Animated right-arrow on hover, `translateY(-5px)` card lift
- Cards link to individual detail pages:

| Card | Links to | Meta shown |
|------|----------|------------|
| Diabetic Ulcer | `diabetic-ulcer.html` | 1 clinical study · 4 case reports |
| Pressure Ulcer | `pressure-ulcer.html` | 1 clinical study · 2 case reports |
| Leg Ulcer | `leg-ulcer.html` | 1 clinical study · 2 case reports |
| Surgical Wound | `surgical-wound.html` | 1 clinical study · 2 case reports |

---

### Page 3 — Abilar Vet Evidence (`abilar-vet.html`)
- 2 side-by-side veterinary study cards (standard study-card layout)
- **Study 1**: Piglet Wounds — controlled veterinary study
- **Study 2**: Laser Wounds — CO₂ laser-induced wound model

---

### Page 4 — Diabetic Ulcer (`diabetic-ulcer.html`) ← Most complete

#### Box 1 — Clinical Study (flip card) *(upgraded in Session 2)*
**Front face (default):**
- Dark green header bar with "Clinical Study" heading + flip icon
- Clicking/tapping the header flips the entire card
- Study description: 35 outpatients, PEDIS grade 1–2, Abilar resin salve (n=19) vs octenidine solution (n=16), 145-day average follow-up, 4 follow-up visits
- Key Findings block: 47% complete healing (resin) vs 31% (octenidine); median prior duration 377 days before entering study

**Back face (on flip):**
- Left column (~60% width): journal cover screenshot (`diabetic-study-cover.png`)
- Right column (~40% width):
  - **Download** button → downloads `diabetic-ulcer-study.pdf` as `Abilar_Diabetic_Ulcer_Clinical_Study.pdf`
  - **Reference** (small text): Korzon-Burakowska A et al., *J Clin Exp Dermatol Res.* 2017;8(6):434. doi:10.4172/2155-9554.1000434
  - "← Back to study" link flips card back

#### Box 2 — Case Studies (2×2 grid with images) *(upgraded in Session 2)*
Each case subbox contains: case number, description text, sensitive image (blurred with warning overlay), caption, reference.

| Case | Patient | Image | Caption | Reference |
|------|---------|-------|---------|-----------|
| Case 1 | 72yo diabetic man, wound → ⅓ size in 1.5 months | `diabetic-case-1.png` | Foot incision wound due to gangrene and infection, and 1 month later | Hevér T., BJSTR 2024;57(4). doi:10.26717/BJSTR.2024.57.009043 |
| Case 2 | 68yo man, forefoot amputation, stagnant 2 months, granulation in 1 month | `diabetic-case-2.png` | Forefoot amputation wound due to gangrene and diabetes infection, and 1 month later | Hevér T., BJSTR 2024;57(4). doi:10.26717/BJSTR.2024.57.009043 |
| Case 3 | 63yo DTII male, toe amputation wound → metatarsal ulcer, improved in 1 month | `diabetic-case-3.png` | Diabetic foot ulcer before Abilar treatment and 1 month later | Non-public |
| Case 4 | 58yo DTII male, non-infected diabetic foot, fully healed in 1 month | `diabetic-case-4.png` | Diabetic foot ulcer before Abilar treatment and 1 month later | Non-public |

**Sensitive image behaviour:**
- All 4 images are **blurred by default** (`filter: blur(12px)`)
- A warning overlay shows: ⚠️ "Sensitive medical image" + "Click to view"
- Clicking/tapping toggles `.revealed` class → blur fades out, warning disappears
- Keyboard accessible (Enter / Space)

#### Box 3 — Expert Opinion *(added in Session 2)*
- Dark green header: "Expert Opinion"
- **Expert profile row**: circular avatar photo (`expert-jokinen.png`), 🇫🇮 flag, name, full title, institution
  - **Dr. Janne Jokinen** — Cardiac and Thoracic Surgery Specialist & General Practitioner, Päijät-Häme Central Hospital, Lahti, Finland
- **Quote grid** (2 columns): two citation cards, each with:
  - Large decorative `"` quotation mark in sage green
  - Italic quote text
  - Divider rule
  - Name + role/institution repeated below
- Quote 1: On Abilar as first-line choice for chronic surgical wounds post-thoracic procedures
- Quote 2: On Abilar's effectiveness even in presence of bacterial colonisation / biofilm

---

### Page 5 — Pressure Ulcer (`pressure-ulcer.html`)

#### Box 1 — Clinical Study *(real data added Session 2)*
- **Study**: Prospective, randomized, controlled multicentre trial; 37 patients, Grade II–IV pressure ulcers, 11 primary care hospitals; resin salve (n=13) vs sodium carboxymethylcellulose hydrocolloid ± ionic silver (n=9); 6-month follow-up, monthly digital photography + planimetric analysis
- **Key Findings**: 94% (17/18) complete healing with Abilar vs 36% (4/11) control (p=0.003); superior effect statistically evident at 3 months (p=0.013); faster bacterial clearance at 1 month

#### Box 2 — Case Studies *(placeholder — to be updated)*
| Case | Description |
|------|-------------|
| Case 1 | 78yo bedridden patient, Grade III sacral ulcer, 60% wound reduction in 8 weeks |
| Case 2 | 65yo post-op ICU patient, Grade II heel ulcer, active granulation in 3 weeks |

---

### Page 6 — Leg Ulcer (`leg-ulcer.html`)

#### Box 1 — Clinical Study *(real data added Session 2)*
- **Study**: Prospective 6-month study; 40 patients (35 preoperative chronic + 5 postoperative SSI) with Critical Limb Ischaemia following peripheral rearterialization; Abilar resin salve (n=20) vs medical honey salve (n=20); at-home care; healing assessed clinically + linear regression of wound size
- **Key Findings**: 77% (17/22) treatment success; 74% chronic foot ulcer healing (excl. SSI); mean healing time 61 ± 41 days

#### Box 2 — Case Studies *(placeholder — to be updated)*
| Case | Description |
|------|-------------|
| Case 1 | 71yo woman, venous ulcer 18 months, complete closure at 14 weeks |
| Case 2 | 63yo man, bilateral ulcers, slough → granulation in 6 weeks |

---

### Page 7 — Surgical Wound (`surgical-wound.html`)

#### Box 1 — Clinical Study *(real data added Session 2)*
- **Study**: Pilot clinical trial; 23 patients with chronic complicated surgical wounds failing primary healing; at-home Abilar application; wound expert review every 2 weeks; monitored wound dimensions + microbial cultures
- **Key Findings**: 100% complete healing; mean 43 ± 24 days (range 10–87 days); bacterial positivity at baseline did NOT significantly prolong healing (attributed to biofilm dispersion)

#### Box 2 — Case Studies *(placeholder — to be updated)*
| Case | Description |
|------|-------------|
| Case 1 | 55yo, dehisced abdominal wound, full re-approximation in 6 weeks, avoided revision |
| Case 2 | 61yo, post-mastectomy wound complication, complete epithelialization in 5 weeks, avoided re-surgery |

---

## Design System

### Color Palette
| Variable | Hex | Usage |
|----------|-----|-------|
| `--color-primary` | `#38473a` | Buttons, headers, accents, footer, map highlight |
| `--color-primary-dark` | `#2d392e` | Hover states |
| `--color-primary-light` | `#4a5e4c` | Case studies header, map hover |
| `--color-white` | `#ffffff` | Text on dark, card backgrounds |
| `--color-bg` | `#f5f5f0` | Page background |
| `--color-text` | `#1a1a1a` | Body text |
| `--color-text-muted` | `#666666` | Descriptions, meta, captions, references |
| `--color-border` | `#deded6` | Card borders, dividers |

### Typography
| Variable | Font | Usage |
|----------|------|-------|
| `--font-heading` | Archivo Narrow 700 | All headings (h1–h4) |
| `--font-body` | Archivo 400/700 | Body text, labels, tags |

Both fonts loaded from **Google Fonts**.

### Shadows
| Variable | Value |
|----------|-------|
| `--shadow-sm` | `0 2px 8px rgba(0,0,0,0.07)` |
| `--shadow-md` | `0 4px 20px rgba(0,0,0,0.11)` |
| `--shadow-lg` | `0 8px 36px rgba(56,71,58,0.22)` |

### Animations
- **`.fade-in`** — `fadeInUp` keyframe (opacity 0→1, translateY 18px→0, 0.6s)
- Delay variants: `--delay-1` through `--delay-6` (0.08s increments)
- All interactive cards have `transform: translateY(-5px)` lift on hover
- **Flip card**: CSS 3D `rotateY(180deg)` on `.is-flipped` class; `perspective: 1200px`
- **Image blur reveal**: `filter: blur(12px)` → `blur(0)` on `.revealed`; transition 0.4s

---

## Key CSS Classes (styles.css — v8)

### Shared / Global
| Class | Purpose |
|-------|---------|
| `.page-wrapper` | Full-height flex column |
| `.site-header` | Dark green top bar with logo + back arrow |
| `.site-footer` | Dark green bottom bar |
| `.site-logo` | Centred ABILAR wordmark |
| `.back-link` | Left-aligned chevron + "Back" text |
| `.fade-in` / `.fade-in--delay-N` | Entry animation utility |

### Page 2 — Map & Presence
| Class | Purpose |
|-------|---------|
| `.presence-card` | White card wrapping map + tags |
| `.presence-card__header` | Dark green label row |
| `#abilar-map` | amCharts 5 mount point (height: 340px) |
| `.presence-card__tags` | Flex row of country pill badges |
| `.presence-tag` | Individual country pill |

### Detail Pages — Clinical Study
| Class | Purpose |
|-------|---------|
| `.flip-card` | 3D flip wrapper (preserves 3D) |
| `.flip-card__face--front` | Front face (study text) |
| `.flip-card__face--back` | Back face (image + download + ref) |
| `.flip-card__icon` | Flip hint icon in header |
| `.flip-back__image-col` | Left column of back face (~60%) |
| `.flip-back__info-col` | Right column of back face (~40%) |
| `.flip-back__download-btn` | Compact inline download link |
| `.flip-back__ref-text` | Small reference citation text |
| `.clinical-card` | Standard (non-flip) clinical study card |
| `.clinical-card__header` | Dark green header bar |
| `.clinical-card__finding` | Left-bordered key findings callout |

### Detail Pages — Case Studies
| Class | Purpose |
|-------|---------|
| `.case-card` | Outer case studies card |
| `.case-card__header` | Medium green header bar |
| `.case-card__grid` | 2-column grid (default — 2 cases) |
| `.case-card__grid--four` | 2×2 grid (4 cases with images) |
| `.case-subbox` | Individual case cell |
| `.case-img-wrapper` | Clickable blur/reveal container |
| `.case-img-wrapper.revealed` | State: blur removed, warning hidden |
| `.case-img-warning` | Overlay with ⚠️ icon + text |
| `.case-subbox__img` | Clinical photo (max-height: 200px) |
| `.case-subbox__caption` | Italic image caption |
| `.case-subbox__ref` | Reference block (small, top-bordered) |
| `.case-subbox__ref-label` | "REFERENCE" uppercase label |

### Detail Pages — Expert Opinion
| Class | Purpose |
|-------|---------|
| `.expert-card` | Outer expert opinion card |
| `.expert-card__header` | Dark green header bar |
| `.expert-profile` | Flex row: avatar + text info |
| `.expert-profile__avatar` | Circular portrait (80×80px) |
| `.expert-profile__flag` | Country flag emoji |
| `.expert-profile__name` | Expert name (bold) |
| `.expert-profile__title` | Specialty title (muted) |
| `.expert-profile__inst` | Institution (muted, small) |
| `.expert-card__grid` | 2-column quote grid |
| `.quote-item` | Individual quote card (white, bordered) |
| `.quote-item__mark` | Large decorative `"` in sage green |
| `.quote-item__text` | Italic quote body |
| `.quote-item__rule` | Horizontal divider |
| `.quote-item__name` | Expert name below divider |
| `.quote-item__role` | Role/institution below name |

---

## Navigation Flow

```
index.html
├── → abilar.html
│   ├── [map: Global Presence — 10 countries highlighted]
│   ├── → diabetic-ulcer.html  ← Back → abilar.html
│   │     Box 1: Flip card (clinical study + PDF download)
│   │     Box 2: 4 case reports with blurred images
│   │     Box 3: Expert opinion (Dr. Janne Jokinen)
│   ├── → pressure-ulcer.html  ← Back → abilar.html
│   │     Box 1: Clinical study (real data)
│   │     Box 2: 2 case reports (placeholder)
│   ├── → leg-ulcer.html       ← Back → abilar.html
│   │     Box 1: Clinical study (real data)
│   │     Box 2: 2 case reports (placeholder)
│   └── → surgical-wound.html  ← Back → abilar.html
│         Box 1: Clinical study (real data)
│         Box 2: 2 case reports (placeholder)
└── → abilar-vet.html          ← Back → index.html
      2 veterinary study cards
```

All pages include:
- **Header**: Sage green bar with centred `ABILAR` logo (links to `index.html`)
- **Back arrow**: Top-left of header on all inner pages
- **Footer**: Sage green bar with copyright and link to abilar.com

---

## Assets (RepolarProject/assets/)

| File | Used in | Description |
|------|---------|-------------|
| `diabetic-ulcer-study.pdf` | `diabetic-ulcer.html` flip card | Downloadable clinical study PDF |
| `diabetic-study-cover.png` | `diabetic-ulcer.html` flip card back | Journal cover screenshot |
| `diabetic-case-1.png` | `diabetic-ulcer.html` Case 1 | Foot incision wound before/after |
| `diabetic-case-2.png` | `diabetic-ulcer.html` Case 2 | Forefoot amputation wound before/after |
| `diabetic-case-3.png` | `diabetic-ulcer.html` Case 3 | Diabetic foot ulcer before/after |
| `diabetic-case-4.png` | `diabetic-ulcer.html` Case 4 | Diabetic foot ulcer before/after |
| `expert-jokinen.png` | `diabetic-ulcer.html` Box 3 | Dr. Janne Jokinen portrait |

---

## What Still Needs to be Done

### High priority
- [ ] **Pressure Ulcer** — Case Studies: add real patient images, captions, references
- [ ] **Leg Ulcer** — Case Studies: add real patient images, captions, references
- [ ] **Surgical Wound** — Case Studies: add real patient images, captions, references
- [ ] **Clinical Study flip cards** for Pressure Ulcer, Leg Ulcer, Surgical Wound (add PDF + journal cover, enable flip interaction)
- [ ] **Expert Opinion boxes** for Pressure Ulcer, Leg Ulcer, Surgical Wound pages

### Nice to have
- [ ] Abilar Vet page: add case studies / images if available
- [ ] Add more experts to the Expert Opinion grid (other countries)
- [ ] Mobile layout review & polish
- [ ] Add a "References" or "Publications" listing page

---

## Dev Server

Configured in `.claude/launch.json`:

```json
{
  "version": "0.0.1",
  "configurations": [
    {
      "name": "Static Dev Server",
      "runtimeExecutable": "python3",
      "runtimeArgs": ["-m", "http.server", "3000"],
      "port": 3000
    }
  ]
}
```

**Start with:** open `http://localhost:3000` after running the server.

> **Note on CSS caching:** All HTML files reference `styles.css?v=N`. After any CSS edits, bump the version number across all HTML files to force browsers to reload the updated stylesheet. Current version: `v=8` (diabetic-ulcer.html), `v=7` (abilar.html), `v=2` (all others).

---

## External Libraries

| Library | Version | Loaded via | Used for |
|---------|---------|------------|---------|
| Google Fonts (Archivo, Archivo Narrow) | — | CSS `@import` | All typography |
| amCharts 5 | 5.x (CDN) | `<script>` tags in `abilar.html` | Interactive world map |

---

## Reference

- Design reference: [https://abilar.com/en-fi](https://abilar.com/en-fi)
- Hero background image: abilar.com CDN (`woman-in-forest-looking-up-at-trees-misty-morning.jpg`)
- Stack: Plain HTML5 / CSS3 / vanilla JS (no framework)
- Source images: `/Users/the_kamma/Desktop/Repolar/Screenshots /`
- Source PDFs: `/Users/the_kamma/Downloads/Clinical studies and other relevant studies regarding Abilar and Abicin/`
