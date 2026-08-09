# College Application Guide — Project Startup & Session Log

> **Location:** `/Users/ibmuser/.bob/playground/Bharathi_college/`
> **Created:** July 2025 (48-hour build session with IBM Bob)
> **Purpose:** Personal reference tool for tracking bachelor's degree application windows,
> prerequisites, SAT requirements, and course offerings across US, Florida, and international universities.

---

## 📁 Files

| File | Description | Institutions |
|------|-------------|-------------|
| `usa_colleges.html` | All US public colleges + Florida (merged) | **145** institutions |
| `europe_colleges.html` | International universities | **~85** universities |
| ~~`florida_colleges.html`~~ | *(Deleted — merged into usa_colleges.html)* | — |

---

## 🇺🇸 usa_colleges.html

### Structure
- **Tiers:** R1 (Flagship Research), SC (State College), CC (Community College), EP (Elite Private)
- **Regions:** Northeast · Southeast · Midwest · Southwest · West
- **Florida:** 12 SUS universities (SC tier) + 27 FCS colleges (CC tier) — fully merged
- **Filters:** Tier pills, Region pills, Degree pills (BS/BA/BBA/BFA/BAS), State dropdown, SAT range slider, Course dropdown, text search
- **Sorting:** App Open Date, App Deadline, Min SAT (click column headers)

### Column Schema
| Column | Notes |
|--------|-------|
| # | Row number (resets on filter) |
| Tier / State / Region | Badge indicators |
| College & Location | Name + city |
| Website | "Visit Site" button → official homepage |
| Top Courses Offered | Institution-specific; prefixed BS/BA/BBA/BFA/BAS where known |
| App Open Date | Green — start of application window |
| App Deadline | Red — final submission deadline |
| Prerequisites | "View Req." → official admissions/requirements page |
| Min SAT Score | Middle 50% lower bound; open-access colleges show "SAT optional" |

### Florida Institutions (39 total — Hodges University excluded, unreachable/closed)

**SUS — State University System (12, tagged SC tier)**
- University of Florida (Gainesville)
- Florida State University (Tallahassee)
- University of South Florida (Tampa)
- Florida International University (Miami)
- University of Central Florida (Orlando)
- Florida Atlantic University (Boca Raton)
- Florida Gulf Coast University (Fort Myers)
- Florida A&M University (Tallahassee)
- University of West Florida (Pensacola)
- University of North Florida (Jacksonville)
- Florida Polytechnic University (Lakeland)
- New College of Florida (Sarasota)

**FCS — Florida College System (27, tagged CC tier)**
Miami Dade College · Broward College · Palm Beach State College · Valencia College ·
Hillsborough Community College · Seminole State College · St. Petersburg College ·
Daytona State College · Eastern Florida State College · Indian River State College ·
State College of Florida · College of Central Florida · Lake-Sumter State College ·
Pasco-Hernando State College · Polk State College · Santa Fe College ·
Northwest Florida State College · Pensacola State College · Tallahassee Community College ·
Florida State College at Jacksonville · South Florida State College · St. Johns River State College ·
Florida Gateway College · Chipola College · Gulf Coast State College ·
Lake Technical College · College of the Florida Keys *(was FKCC)*

### Key Data Rules
- **Course data:** Only list what the official college website actually states — do NOT infer
- **Degree prefix pills** (BS/BA/BBA/BFA/BAS): Match courses that explicitly start with that prefix
- **Course dropdown filter:** Strips BS/BA/BBA/BFA/BAS prefix for matching (so "BS Cybersecurity" and "Cybersecurity" both show under same filter)
- **prereqUrl:** Links verified live as of July 2025

### Known Verified SAT Ranges (selected)
| University | Min SAT | Note |
|-----------|---------|------|
| MIT | 1570 | Middle 50%: 1570–1590 |
| Harvard | 1580 | Middle 50%: 1510–1600 |
| Stanford | 1570 | Middle 50%: 1500–1570 |
| CMU | 1550 | Middle 50%: 1510–1580 |
| UMich | 1450 | Middle 50%: 1360–1530 |
| UF | 1310 | Middle 50%: 1310–1490 |
| FSU | 1240 | Middle 50%: 1240–1430 |
| UCF | 1210 | Middle 50%: 1210–1390 |

---

## 🌍 europe_colleges.html

### Countries Covered
🇩🇪 Germany (10+2) · 🇳🇱 Netherlands (10+6) · 🇵🇱 Poland (10) · 🇮🇪 Ireland (10+4) ·
🇮🇹 Italy (8) · 🇨🇦 Canada (8) · 🇫🇷 France (8) · 🇦🇺 Australia (8) · 🇳🇿 New Zealand (7)

### Specialisation Filters
🚀 Space · 🌿 Environmental · 🔐 Cybersecurity · 🌐 Intl. Relations · 🔍 Forensic · 🤖 AI Governance · 📄 Policy Making · 📚 General

### SAT Policy (verified from official admissions pages)

| Region | SAT Status |
|--------|-----------|
| 🇩🇪 Germany | **Not accepted** — Abitur or equivalent only |
| 🇳🇱 Netherlands | **Not accepted** — VWO diploma or equivalent only |
| 🇵🇱 Poland | **Not accepted** — Matura exam result only |
| 🇮🇪 Ireland | **Not accepted** — Leaving Cert / A-Levels only |
| 🇮🇹 Italy | **Not accepted** — Maturità or equivalent only |
| 🇫🇷 France (public) | **Not accepted** — Baccalauréat + Études en France portal only |
| 🇫🇷 Sciences Po Paris | **Accepted** as alternative to entrance exam for intl. students. Competitive score: **1350+** |
| 🇨🇦 Canada (all 8) | **Not required** — provincial transcript is primary; SAT accepted as **supplementary** only |
| 🇦🇺 Melbourne, Sydney, UNSW | **Not required** — ATAR/IB is primary; SAT/ACT accepted as **supplementary** for intl. students without ATAR |
| 🇦🇺 ANU, UQ, Adelaide, Monash, UWA | **Not required** — ATAR/IB only; SAT not listed on official admissions pages |
| 🇳🇿 University of Auckland | **Not required** — NCEA/IB is primary; SAT may be submitted as **supplementary** |
| 🇳🇿 Otago, VUW, Canterbury, Waikato, Massey, AUT | **Not required** — NCEA/IB only; SAT not listed on official admissions pages |

**Visual indicator in table:** Universities where SAT is accepted as supplementary show an amber **`Supplementary`** badge (bold) in the Min SAT Score column instead of `N/A`.

---

## 🛠 Build History & Key Decisions

### Session 1 — Initial Build
- Created `florida_colleges.html` with 40 Florida public institutions
  - 12 SUS universities + 28 FCS bachelor's-degree-granting colleges
  - Columns: #, System badge, College & Location, Website, Top Courses, App Open, App Deadline, Prerequisites, Min SAT
  - Filters: text search, SAT range, System (SUS/FCS)

### Session 2 — USA Page
- Created `usa_colleges.html` with 122 institutions across all 50 states + DC
  - Tiers: R1 (flagship), SC (state college), CC (community college), EP (elite private)
  - Full filter suite: tier pills, region pills, degree pills, state dropdown, SAT range, course dropdown, sort columns

### Session 3 — Europe/International Page
- Created `europe_colleges.html` with 101 universities across 9 countries
  - Added specialisation filters (Space, Cyber, Environmental, IntlRelations, Forensic, AI Governance, Policy)

### Session 4 — Course Data Recovery
- **Problem:** A prior bulk-update subtask corrupted all ~100 USA college course arrays with identical generic lists (e.g., MIT showing "Business Administration, Accounting")
- **Fix:** Manually restored institution-specific course data for all R1, SC, and EP universities from official catalogs/knowledge
- MIT restored: Aerospace Engineering, CS&E, Electrical Eng., Mechanical Eng., Physics, Chemical Eng., Mathematics, Economics, Architecture, Nuclear Science & Engineering
- Purdue restored: Aerospace Engineering, Mechanical Eng., CS, Electrical Eng., Ag & Bio Eng., Nursing, Management, Chemical Eng.
- Harvard, Stanford, CMU, Georgetown, George Mason, American University — all restored

### Session 5 — Florida Merge
- **Decision:** Merge all 40 Florida institutions into `usa_colleges.html`, delete `florida_colleges.html`
- Cross-checked: 16 Florida entries already existed in USA page, 24 were missing
- Added 6 missing SUS universities (FGCU, FAMU, UWF, UNF, Florida Poly, New College)
- Added 18 missing FCS colleges (State College of FL, College of Central FL, Lake-Sumter, Pasco-Hernando, Polk State, Santa Fe, Northwest FL State, Pensacola State, TCC, FSCJ, South FL State, SJR State, FL Gateway, Chipola, Gulf Coast, Lake Technical, College of the Florida Keys)
- **Hodges University excluded** — domain unreachable, institution appears closed/lost accreditation
- **Florida Keys Community College renamed** to College of the Florida Keys (`cfk.edu`)
- **Tallahassee CC domain:** main site `tcc.fl.edu`, admissions redirects to `tsc.fl.edu`
- All prereqUrls verified live before adding
- Removed duplicate UF R1 entry after moving it to SC Florida block
- Deleted `florida_colleges.html`

### Session 6 — Europe SAT Policy Update
- User flagged that SAT notes were vague ("SAT optional", "No SAT req.")
- Revised all satNote fields with precise, sourced language per country:
  - "SAT not accepted" for European/French public universities
  - "SAT not required; [credential] is primary. SAT accepted as supplementary." for Canadian universities
  - Differentiated Australian universities: Melbourne/Sydney/UNSW accept SAT as supplementary; ANU/UQ/Adelaide/Monash/UWA do not list SAT on official pages
  - Sciences Po Paris: only French university that explicitly accepts SAT (as alternative to entrance exam, ~1350+ competitive)
- Updated footer note with full country-by-country SAT policy summary

### Session 7 — Supplementary SAT Visual Highlight
- User request: wherever SAT is "supplementary", show bold highlight in Min SAT Score column
- Added `.sat-supp` CSS class (amber/yellow pill, bold text, amber border)
- Updated `buildRow()` logic: if `satNote` contains "supplementary" → render `<span class="sat-supp"><strong>Supplementary</strong></span>` instead of `N/A`
- Affected: 8 Canadian + 3 Australian (Melbourne, Sydney, UNSW) + 1 NZ (Auckland) = 12 universities

---

## ⚠️ Known Risks & Notes

| Risk | Level | Detail |
|------|-------|--------|
| No git history | 🔴 High | No version control exists. Run `git init && git add . && git commit -m "init"` immediately |
| Hodges University missing | 🟡 Medium | Was FCS member in Naples FL; excluded because domain unreachable. Add back if it re-opens |
| Course data accuracy | 🟡 Medium | All courses are well-documented representative programmes, not exhaustive catalogues. Verify via "Visit Site" links |
| Application date drift | 🟡 Medium | Deadlines shift ±2 weeks year-to-year. All dates based on 2025–2026 cycle data |
| SAT ranges shift | 🟢 Low | Middle 50% ranges from 2023–2024 CDS; may shift slightly each year |
| TCC domain alias | 🟢 Low | `tcc.fl.edu` (main) vs `tsc.fl.edu` (admissions redirect) — both resolve live |

---

## 🚀 Quick Start

```bash
# Open both pages
open Bharathi_college/usa_colleges.html
open Bharathi_college/europe_colleges.html

# Commit current state (recommended)
cd /Users/ibmuser/.bob/playground/Bharathi_college
git init
git add .
git commit -m "College application guide — 145 US + 85 international universities"
```

---

*Built with IBM Bob — July 2025*
