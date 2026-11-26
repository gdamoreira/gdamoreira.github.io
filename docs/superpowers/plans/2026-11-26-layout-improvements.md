# Layout & Text Improvements Implementation Plan (About Me, Career Highlights, Get in Touch)

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Implement the layout and text updates shown in the three visual reference designs:
1. `about-me.png`: Left sidebar with profile links and Toptal badge; right side with "Open for Staff Engineer" callout banner with tag pills, updated bio copy, Snodra link, and contact CTA.
2. `career-highlights.png`: Replace Projects with "Career highlights" featuring a full-width lead card (A US$100 million exit) and a 3-column grid of 6 proof-point cards, followed by a LinkedIn timeline footer.
3. `get-in-touch.png`: Centered contact section with position pitch, LinkedIn connection link, prominent outline "Email Guilherme" button, and direct email reference.

**Architecture:**
- Create customized Jekyll include templates (`_includes/about.html`, `_includes/section-career-highlights.html`, `_includes/section-get-in-touch.html`, and `_includes/header.html`).
- Update SCSS styling in `assets/main.scss` with clean, modern, responsive CSS rules matching the exact typography, card borders, pill badges, and button styling from the screenshots.
- Update `_config.yml` configuration (title, email, domain, content structure) with the exact text and data structure.

**Tech Stack:** Jekyll, Liquid, SASS/SCSS, HTML5, CSS Grid/Flexbox, Font Awesome.

---

## Global Constraints

- Domain and email in header and footer updated to `damoreira.com` and `guilherme@damoreira.com`.
- Preserves responsive design across desktop, tablet, and mobile (collapsing 3-column highlight grid cleanly).
- Preserves print stylesheet compatibility (`no-print` classes where appropriate).
- No broken links or placeholder text.
- Valid YAML and zero Jekyll build errors.

---

## Tasks

### Task 1: Header & Global Config Updates (`_config.yml` & `_includes/header.html`)

**Files:**
- Modify: `_config.yml`
- Create: `_includes/header.html`

- [ ] **Step 1: Update `_config.yml` personal info and metadata**
  - Update `title: Staff / Senior Software Engineer`
  - Update `tagline: Distributed Systems Architecture & Application Security`
  - Update `email: guilherme@damoreira.com`
  - Update `website: damoreira.com`
  - Update `additional_links` to use `https://damoreira.com`
  - Update SEO description to match Staff/Senior Engineer positioning.

- [ ] **Step 2: Create `_includes/header.html` to support subtitle/tagline**
  - Render name, title, and tagline:
    ```html
    <h1>{{ site.name | escape }}</h1>
    <h2>{{ site.title | escape }}</h2>
    {% if site.tagline %}
      <p class="header-tagline">{{ site.tagline | escape }}</p>
    {% endif %}
    ```
  - Ensure header email and web links point to `damoreira.com`.

- [ ] **Step 3: Add SCSS for header tagline in `assets/main.scss`**
  - Style `.header-tagline` with appropriate font size and muted color.

- [ ] **Step 4: Verify build**
  - Run docker build or ruby check to confirm clean compilation.

---

### Task 2: Implement "About Me" Layout & Content (`_includes/about.html` & `assets/main.scss`)

**Files:**
- Modify: `_includes/about.html`
- Modify: `assets/main.scss`
- Modify: `_config.yml` (about_content)

- [ ] **Step 1: Update left column in `_includes/about.html`**
  - Render profile avatar image.
  - Add quick profile action links below avatar:
    - LinkedIn icon + "View LinkedIn Profile" (`https://www.linkedin.com/in/gdamoreira`)
    - Envelope icon + "Email me" (`mailto:guilherme@damoreira.com`)
  - Render Toptal badge below action links.

- [ ] **Step 2: Update right column with Callout Banner and Bio Copy**
  - Create callout card component:
    - Eyebrow: `GUILHERME D'AMOREIRA · SENIOR SOFTWARE ENGINEER`
    - Headline: `Open for Staff Engineer, Tech Lead & Software Architect roles`
    - Pill badges:
      - `● Barcelona · Remote-friendly` (green dot)
      - `15+ yrs backend architecture`
      - `Distributed systems`
      - `Application security`
      - `JVM · Kotlin · Kafka`
  - Add the 3 body paragraphs:
    1. 15+ years designing distributed backend platforms across PropTech, cybersecurity, FinTech, and enterprise SaaS.
    2. JVM home ground (Kotlin, Java, Quarkus, Spring Boot, Kafka, Postgres, AWS, Kubernetes) & Oracle AppSec background.
    3. Scale and leadership: US$100M exit, CTO experience, backend standards, and author of [Snodra](https://snodra.damoreira.com).
  - Add closing CTA:
    "Hiring for a Staff Engineer, Tech Lead or Software Architect role? Reach me on [LinkedIn](https://www.linkedin.com/in/gdamoreira) or email [guilherme@damoreira.com](mailto:guilherme@damoreira.com)."

- [ ] **Step 3: Add SCSS styling for About Me components in `assets/main.scss`**
  - Style `.profile-links`, `.about-hero-card`, `.eyebrow`, `.headline`, `.badge-pills`, `.status-dot`, and `.about-cta`.

- [ ] **Step 4: Verify Jekyll build**
  - Build site and verify HTML matches `about-me.png`.

---

### Task 3: Implement "Career Highlights" Section (`_includes/section-career-highlights.html` & `_config.yml`)

**Files:**
- Create: `_includes/section-career-highlights.html`
- Modify: `_config.yml`
- Modify: `assets/main.scss`

- [ ] **Step 1: Define Career Highlights data in `_config.yml`**
  - Add section with `title: Career highlights`, `layout: career-highlights`.
  - Include subtitle: "Seven proof points across distributed systems, application security, and engineering leadership — delivered at enterprise scale."
  - Configure `lead_card`:
    - Tag: `SCALE & IMPACT`
    - Title: `A US$100 million exit`
    - Description: "Tech lead on the 3D production platform that took Decora from about 15 people to over 150 and to its acquisition by CreativeDrive — the second-largest Brazilian tech deal of 2018."
  - Configure 6 grid cards:
    1. `DISTRIBUTED SYSTEMS` - Real-time platform architecture (Beyonnex)
    2. `APPLICATION SECURITY` - Security built into engineering (Oracle NetSuite)
    3. `PLATFORM OWNERSHIP` - Enterprise ASPM delivery (Phoenix Security)
    4. `LEADERSHIP` - Executive experience (Reticomm)
    5. `OPEN SOURCE` - Author of Snodra (Snodra router, Kotlin/Rust/Go libraries with link)
    6. `VETTING` - Vetted and trained (Toptal & Black Hat certifications)
  - Configure section footer:
    - Text: "See the full timeline, endorsements, and shared connections."
    - Link: `View full profile on LinkedIn` (`https://www.linkedin.com/in/gdamoreira`)

- [ ] **Step 2: Create `_includes/section-career-highlights.html`**
  - Render subtitle.
  - Render lead card with prominent left border accent.
  - Render 3-column responsive card grid.
  - Render footer note and LinkedIn profile link.

- [ ] **Step 3: Add SCSS styling in `assets/main.scss`**
  - Styles for `.highlights-subtitle`, `.highlight-card`, `.lead-card`, `.highlight-grid`, `.highlight-tag`, and `.highlights-footer`.
  - Responsive media query: 3 columns on desktop (>992px), 2 columns on tablet (768-992px), 1 column on mobile (<768px).

- [ ] **Step 4: Verify Jekyll build**
  - Build site and verify HTML and layout match `career-highlights.png`.

---

### Task 4: Implement "Get in Touch" Section (`_includes/section-get-in-touch.html` & `_config.yml`)

**Files:**
- Create: `_includes/section-get-in-touch.html`
- Modify: `_config.yml`
- Modify: `assets/main.scss`

- [ ] **Step 1: Configure Get in Touch in `_config.yml`**
  - Section title: `Get in touch`
  - Layout: `get-in-touch`
  - Content parameters: pitch, LinkedIn link, email button text, direct email address.

- [ ] **Step 2: Create `_includes/section-get-in-touch.html`**
  - Centered intro text: "Open to **Staff Engineer, Tech Lead and Software Architect** roles — remote or Barcelona, ideally where distributed systems and security meet. Happy to talk."
  - Centered LinkedIn icon with text "Connect on LinkedIn".
  - Outline button: `[ ✉ Email Guilherme ]` linking to `mailto:guilherme@damoreira.com`.
  - Direct email line: `Direct: guilherme@damoreira.com`.

- [ ] **Step 3: Add SCSS styling in `assets/main.scss`**
  - Styles for `.get-in-touch-box`, `.contact-pitch`, `.contact-linkedin-link`, `.contact-email-btn`, and `.contact-direct-text`.

- [ ] **Step 4: Verify Jekyll build**
  - Build site and verify HTML and layout match `get-in-touch.png`.

---

### Task 5: End-to-End Verification and Visual Check

- [ ] **Step 1: Run full Jekyll build inside Docker container**
  - `docker run --rm -v "$PWD":/srv/jekyll -w /srv/jekyll jekyll/jekyll:3.8 jekyll build`
  - Confirm exit code 0.

- [ ] **Step 2: Launch `docker compose up` and test all pages**
  - Verify layout against `about-me.png`, `career-highlights.png`, and `get-in-touch.png`.
  - Test all hyperlinks (LinkedIn, Snodra, email, Toptal).
  - Verify mobile responsiveness and Dark Mode compatibility.
