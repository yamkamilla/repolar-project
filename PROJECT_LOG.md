# Abilar Evidence Microsite — Project Log

A record of all design and development work completed on the Abilar clinical evidence presentation microsite.

---

## Site Structure

| Page | File | Description |
|------|------|-------------|
| Home / Title | `index.html` | Landing page — hero, product selectors, global presence map, expert opinions |
| Abilar (Human) | `abilar.html` | Indication selection — Chronic & Acute wound categories |
| Diabetic Ulcer | `diabetic-ulcer.html` | Clinical study + 4 case reports with blurred images |
| Pressure Ulcer | `pressure-ulcer.html` | Clinical study + 1 case report with blurred image |
| Leg Ulcer | `leg-ulcer.html` | Clinical study + case reports |
| Surgical Wound | `surgical-wound.html` | Clinical study + case reports |
| Abilar Vet | `abilar-vet.html` | Veterinary evidence |
| Burns | `burns.html` | Stub — no content yet |
| Lacerations | `lacerations.html` | Stub — no content yet |
| Abrasions | `abrasions.html` | Stub — no content yet |

---

## Changes Log

### Global Presence Map (index.html)
- Built with **amCharts 5** (`MapChart`, `geoNaturalEarth1` projection)
- Highlighted countries (dark green `#38473a`):
  Finland, Sweden, Norway, Denmark, Germany, Poland, Greece, United Kingdom, Peru, Chile, **China, Japan, Lebanon, Iran, Turkey**
- **Hover card**: floating panel (bottom-left of map) appears on mouseover — shows flag, country name, and for Finland a quote preview with "Click to read more →"
- **Click modal**: full expert profile + two quotes; currently active for Finland (Dr. Janne Jokinen)
- **NHS Approved badge**: gold pill label (`★ NHS Approved`) placed near Greenland (`[-38, 68]`) to avoid overlapping European countries; UK hover card also shows the NHS note
- amCharts logo removed via `root._logo.dispose()`
- Map originally on `abilar.html`; **moved to `index.html`** (Title Page)

### Expert Opinions Section (index.html)
- Added below the Global Presence map on the title page
- Intro: *"Abilar is trusted by key opinion leaders in the industry. Below are professional testimonials from clinicians who use Abilar in their daily practice."*
- **Dr. Janne Jokinen** — Cardiac and Thoracic Surgery Specialist & GP, Päijät-Häme Central Hospital, Lahti, Finland. Photo: `assets/expert-jokinen.jpg`
- **Dr. Arno Sipponen** — Specialist in Orthopedics and Traumatology. Photo: `assets/expert-sipponen.jpg`
- Fixed left-alignment with `text-align: left` on `.expert-opinions-card` (overrides inherited `text-align: center` from `.hero-bottom`)

### Abilar Page — Indications (abilar.html)
- Replaced flat 2×2 grid with **two grouped master boxes**:
  - **Chronic Wounds**: Diabetic Ulcer (01), Pressure Ulcer (02), Leg Ulcer (03)
  - **Acute Wounds**: Surgical Wound (04), Burns (05), Lacerations (06), Abrasions (07)
- New indication stubs added: Burns, Lacerations, Abrasions

### Pressure Ulcer Page (pressure-ulcer.html)
- **Case 1 updated**:
  - Description: 61-year-old male, sacral pressure ulcer from paraplegia, completely healed after 7 months of daily Abilar treatment
  - Image: `assets/pressure-ulcer-case-1.png` — blurred with ⚠️ click-to-reveal overlay (same pattern as diabetic ulcer page)
  - Caption: *"Pressure ulcer before Abilar treatment and 7 months later."*
  - Reference: Non-public
- **Case 2 deleted** (not relevant)
- CSS version bumped to `v=10`

---

## Assets

| File | Description |
|------|-------------|
| `assets/expert-jokinen.jpg` | Photo of Dr. Janne Jokinen |
| `assets/expert-sipponen.jpg` | Photo of Dr. Arno Sipponen |
| `assets/pressure-ulcer-case-1.png` | Pressure ulcer case 1 before/after image |
| `assets/diabetic-case-1.png` | Diabetic ulcer case 1 |
| `assets/diabetic-case-2.png` | Diabetic ulcer case 2 |
| `assets/diabetic-case-3.png` | Diabetic ulcer case 3 |
| `assets/diabetic-case-4.png` | Diabetic ulcer case 4 |
| `assets/diabetic-study-cover.png` | Diabetic ulcer study cover image |

---

## Design System

| Token | Value |
|-------|-------|
| Primary colour | `#38473a` (dark forest green) |
| Font heading | Playfair Display (serif) |
| Font body | Archivo (sans-serif) |
| Card border-radius | `12px` |
| Card border | `1px solid var(--color-border)` |
| Shadow | `var(--shadow-sm)` |

**Patterns:**
- **Green header bar**: used on Indications, Global Presence, Expert Opinions, Clinical Study, Case Studies cards
- **Blurred medical images**: `.case-img-wrapper` with `.revealed` toggle; ⚠️ warning overlay, click to reveal
- **Indication cards**: white card with right-arrow, grouped under category labels
- **Expert cards**: photo avatar (60px circle) + name/title + italic quote with green left border

---

## Pending / Future Work

- Add content to Burns, Lacerations, Abrasions stub pages
- Add expert profiles for additional countries (currently only Finland has a modal)
- Abilar Vet page content
- Leg Ulcer and Surgical Wound case report images
