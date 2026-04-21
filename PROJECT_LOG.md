# Abilar Evidence Microsite — Project Log

A record of all design and development work completed on the Abilar clinical evidence presentation microsite.

---

## Site Structure

| Page | File | Status |
|------|------|--------|
| Home / Title | `index.html` | ✅ Complete |
| Abilar (Human) | `abilar.html` | ✅ Complete |
| Diabetic Ulcer | `diabetic-ulcer.html` | ✅ Complete |
| Pressure Ulcer | `pressure-ulcer.html` | ✅ Complete |
| Leg Ulcer | `leg-ulcer.html` | ✅ Complete |
| Surgical Wound | `surgical-wound.html` | ✅ Complete |
| Burns | `burns.html` | ✅ Complete |
| Lacerations | `lacerations.html` | ✅ Complete |
| Abrasions | `abrasions.html` | ✅ Complete |
| Abilar Vet | `abilar-vet.html` | ✅ Complete |

---

## Page-by-Page Summary

### index.html — Home / Title Page
- Hero section: forest background image, "Evidence-Based Wound Care" tagline
- Two circle buttons → Abilar (Human) / Abilar Vet
- **Global Presence Map** (amCharts 5, geoNaturalEarth1 projection)
  - 15 highlighted countries: Finland, Sweden, Norway, Denmark, Germany, Poland, Greece, UK, Peru, Chile, China, Japan, Lebanon, Iran, Turkey
  - Hover card: floating panel bottom-left, shows flag + country name; Finland shows Jokinen quote preview + "Click to read more →"
  - Click modal: full expert profile + 2 quotes (Finland/Jokinen only currently)
  - **NHS Approved** gold badge at coordinates `[-38, 68]` (near Greenland) — avoids overlapping European countries
  - amCharts logo removed via `root._logo.dispose()`
- **Expert Opinions** section below map
  - Intro text: "Abilar is trusted by key opinion leaders in the industry..."
  - **Dr. Janne Jokinen** — Cardiac & Thoracic Surgery Specialist & GP, Päijät-Häme Central Hospital, Finland. Photo: `assets/expert-jokinen.jpg`
  - **Dr. Arno Sipponen** — Specialist in Orthopedics and Traumatology. Photo: `assets/expert-sipponen.jpg`
  - Text-align: left applied to override hero-bottom centering

### abilar.html — Human Indications
- Section header: "Human Studies / Evidence"
- **Indications card** with two grouped master boxes:
  - **Chronic Wounds**: Diabetic Ulcer (01), Pressure Ulcer (02), Leg Ulcer (03)
  - **Acute Wounds**: Surgical Wound (04), Burns (05), Lacerations (06), Abrasions (07)

### diabetic-ulcer.html
- Flip card: clinical study (RCT, 35 patients, PEDIS grade 1–2, 145-day follow-up)
- Back: journal cover image (`diabetic-study-cover.png`) + PDF download + reference
- 4 case reports with blurred images (click-to-reveal ⚠️ pattern)

### pressure-ulcer.html
- Flip card: clinical study
- Case 1: 61yo male, sacral pressure ulcer from paraplegia, healed in 7 months
  - Image: `assets/pressure-ulcer-case-1.png` (blurred)
  - Caption: "Pressure ulcer before Abilar treatment and 7 months later."
  - Reference: Non-public
- Case 2: deleted (not relevant)

### leg-ulcer.html
- Flip card + case reports (existing content, no updates this session)

### surgical-wound.html
- Flip card + case reports (existing content, no updates this session)

### burns.html
- **Flip card** (Clinical Study):
  - Front: PHMB + resin salve study, 19 pediatric patients, facial burns, 11.2 days avg hospitalisation
  - Key findings: 73% zero pain by day 6, TIME strategy alignment
  - Back: `burns-study-cover.jpg` (converted from `Burns_screenshot.pdf`, cropped to portrait) + PDF download + reference
  - Reference: Olszyna J. Chirurgia Plastyczna i Oparzenia. 2019 Dec;7(4):175–9. doi:10.15374/CHPIO2019026
  - PDF: `assets/burns-clinical-study.pdf`
- **3 case reports** (all blurred, Non-public):
  - Case 1: Female 30yo, cooking oil burn right thigh, healed 5 months. Image: `Burn 1.png`
  - Case 2: Male 70yo, hypertension + AF, boiling water hand burn grade 2, healed 2 weeks. Image: `Burn 2.png`
  - Case 3: Female 44yo, first-degree oil burn, healed 20 days, no scarring. Image: `Burn 3.png`
- **CSS fix**: `overflow: hidden; border-radius` added to `.flip-card__face--back` to contain cover image within card bounds (3D transform bypass issue)

### lacerations.html
- **3 case reports** (no clinical study, all Non-public):
  - Case 1: Male 81yo, Dupuytren's contracture post-op tear → healed day 23. Image: `Laceration 1.png`
  - Case 2: Male 75yo, ankle fracture external fixation laceration → healed day 53. Image: `Laceration 2.png`
  - Case 3: Male 35yo, blunt trauma elbow laceration → healed day 27, mild transient redness. Image: `Laceration 3.png`

### abrasions.html
- **2 case reports** (no clinical study, all Non-public):
  - Case 1: Male 50yo, fingertip pulp abrasion → healed day 65. Image: `Abrasion 1.png`
  - Case 2: Male 54yo, farming equipment hand compression injury → healed day 71. Image: `Abrasion 2.png`

### abilar-vet.html
- Completely rebuilt from old stub to match human evidence page structure
- **Study 1 — Piglet Wounds** (flip card):
  - 95 male piglets, 5 groups, castration wound model, digital planimetry of 647 photos over 17 days
  - Key findings: Abilar highest closure rate (8.95%), lowest fungal colonization (77%)
  - Back: `piglet-study-cover.jpg` + PDF download + reference
  - Reference: Prokop D et al. Planta Med. 2022;88(3–4):300–12. doi:10.1055/a-1646-2959
  - PDF: `Prokop_et_al_Abilar_Piglets_...pdf`
- **Study 2 — Laser Wounds** (flip card):
  - Healthy dogs, ovariohysterectomy wounds, 3 groups: control / Abilar Vet / biostimulation laser
  - Key findings: Abilar suture removal by days 5–6 (vs 7–9 control), easiest stitch removal
  - Back: `laser-study-cover.jpg` + PDF download + reference
  - Reference: Zahrádek F. In: New Options and Procedures in Wound Treatment — Collection of Lectures. 2024.
  - PDF: `Collection of lectures New options and procedures in wound treatment 2024.pdf`

---

## Assets

| File | Used In |
|------|---------|
| `expert-jokinen.jpg` | index.html expert card + Finland modal |
| `expert-sipponen.jpg` | index.html expert card |
| `pressure-ulcer-case-1.png` | pressure-ulcer.html |
| `diabetic-case-1..4.png` | diabetic-ulcer.html |
| `diabetic-study-cover.png` | diabetic-ulcer.html flip back |
| `diabetic-ulcer-study.pdf` | diabetic-ulcer.html download |
| `burns-study-cover.jpg` | burns.html flip back (converted + cropped from Burns_screenshot.pdf) |
| `burns-clinical-study.pdf` | burns.html download |
| `Burns_screenshot.pdf` | source for burns-study-cover.jpg |
| `Burn 1..3.png` | burns.html cases |
| `Laceration 1..3.png` | lacerations.html |
| `Abrasion 1..2.png` | abrasions.html |
| `piglet-study-cover.jpg` | abilar-vet.html Study 1 flip back (converted from Piglet_Screenshot.pdf) |
| `laser-study-cover.jpg` | abilar-vet.html Study 2 flip back (converted from Laser_Screenshot.pdf) |
| `Prokop_et_al_...pdf` | abilar-vet.html Study 1 download |
| `Collection of lectures...2024.pdf` | abilar-vet.html Study 2 download |
| `leg_pdf.pdf`, `pressure_pdf.pdf`, `surgical_pdf.pdf` | respective flip card downloads |

---

## Design System

| Token | Value |
|-------|-------|
| `--color-primary` | `#38473a` (dark forest green) |
| `--color-primary-light` | `#4a5e4c` |
| `--font-heading` | Archivo Narrow 700 |
| `--font-body` | Archivo 400/700 |
| `--radius-card` | `10px` |
| `--shadow-md` | `0 4px 20px rgba(0,0,0,0.11)` |

**Shared patterns:**
- **Green header bar**: all major cards (Indications, Global Presence, Expert Opinions, Clinical Study, Case Studies)
- **Flip card**: front = study content; back = journal cover image + download PDF + reference + "Back to study" link
- **Blurred medical images**: `.case-img-wrapper` + `.revealed` toggle; ⚠️ warning overlay, click to reveal
- **Indication cards**: white card + right-arrow, grouped under category label
- **Expert cards**: 60px circular avatar + name/title + italic quote with green left border
- **Breadcrumb nav**: all detail pages

## Dev Server

- Runs via `npx serve` (switched from Python 3.9 which had `os.getcwd()` permission error)
- Config: `.claude/launch.json` → `npx serve -l 3000 /Users/the_kamma/Desktop/RepolarProject`
- Start: `preview_start` with name "Static Dev Server"
- URL: `http://localhost:3000`
- CSS cache-busting: all pages reference `styles.css?v=10`

---

## Pending / Known Issues

- **Burns flip card image overflow**: `overflow: hidden + border-radius` added to `.flip-card__face--back` in CSS — needs visual confirmation in browser (3D transform bypasses parent clipping; `clip-path` was tried but broke the flip animation)
- **Expert modals**: currently only Finland (Dr. Jokinen) has full modal content; other 14 countries show presence message only
- **Leg Ulcer & Surgical Wound**: case report images not yet added
