# CV Text Improvement Plan — damoreira.com.br

**Date:** 2026-10-23
**Scope:** every reader-facing string in `_config.yml` (SEO description, About, Projects, Experience, Education, hobbies) plus the page title.
**Positioning:** Senior Software Engineer focused on Kotlin and Java, deep in Spring Boot and Quarkus, with event-driven systems, a Python stack, and application security as range.
**Reader:** a hiring manager or recruiter who gives the page 30–60 seconds before deciding whether to read further.
**Goal:** they understand what he does, what he has shipped, and what he would be productive in on day one — and they want to email him.

---

## 1. Diagnosis

The material is strong; the editing is not. Concretely:

1. **Duplicated text.** The CreativeDrive paragraph is pasted twice into itself (line 210), the Softplan paragraph twice (line 251), and the SEO description is verbatim the About content. The live page shows all three.
2. **The same job is told three times.** CreativeDrive appears as a Project (8 paragraphs), an Experience entry, and in About. beyonnex appears twice with nearly identical paragraphs.
3. **Company marketing instead of personal evidence.** Six entries open with the employer's sales copy ("We want to make real estate climate-friendly…", Phoenix's "ACT now…", Oracle's NetSuite vision). None of it says what *he* did.
4. **Buzzword fog.** "Cutting-edge" appears 9 times, alongside "revolutionizing", "empowering", "robust and scalable", "exacting requirements", "high-quality". These are claims, not evidence.
5. **Tense drift.** Jobs that ended years ago are written in the present: "I am responsible", "I have developed", "our team has developed". A reader cannot tell what is current.
6. **Technology dumps.** 20–30 comma-separated items per role, mixing real skills (Kotlin, Kafka, Spring Boot) with tools (IntelliJ, Git, Jira) and platforms (Bamboo, Tomcat). The same list is repeated between roles.
7. **No spine.** There is no skills summary, no consistent role shape, no closing invitation. The email is a small line in the header; nothing asks the reader to use it.
8. **Small but visible errors.** "my name's Guilherme as a software engineer", "This master is for professionals who wants", "bring value to a analysis", "some of other hobbies", "Engineer's degree" for a postgraduate specialisation.
9. **Unused credibility.** Toptal "Top 3%", the 15 → 150 scale-up, the acquisition, Oracle, and the boomerang return to beyonnex are all buried or unmentioned.

Voice target for the rewrite: first person, professional but conversational — the way he would explain his work to a friendly engineer over coffee. Plain words, short sentences, outcomes before technology.

---

## 2. Global voice rules

- First person, contractions allowed ("I've", "I'm"). No "we" when describing personal ownership; "we" only for team outcomes.
- Past tense for every role that ended. Present tense only for beyonnex (current).
- Lead with the outcome, then the how: "Cut render turnaround from days to hours by automating 3ds Max with MaxScript" — not "I was responsible for automation".
- One idea per paragraph, three sentences maximum. No paragraph over ~60 words outside the flagship case study.
- Numbers whenever they exist. Never invent one; if a number is unknown, write a qualitative outcome instead.
- Ban list: cutting-edge, utilize, leverage, robust, scalable (as filler), empowering, revolutionizing, seamless, state-of-the-art, responsible for, passionate, strive, best efforts, exacting, high-quality.
- Tech names written correctly: Kotlin, Java 17, Spring Boot, Quarkus, Kafka, PostgreSQL, 3ds Max, MaxScript, V-Ray, Unity, Unreal Engine, AWS, Docker, Kubernetes.
- US spelling (`organization`, `optimize`), consistent with the current page.
- Every role ends with one line: `**Stack:** …` — six to ten items, chosen for the role, not a dump.

---

## 3. Page structure

Keep the theme's existing section order. Insert one new section and change the shape of the rest.

### 3.1 Header
- Keep the name. Change `title` to `Senior Software Engineer · Kotlin & Java`.
- Keep the Toptal badge; it is third-party proof and belongs beside the face.

### 3.2 About (target: 3 paragraphs, 120–160 words)
1. What he is and has been doing for the last few years: senior backend engineer, Kotlin/Java, Spring Boot and Quarkus, event-driven systems on Kafka, real-time cost and consumption platforms.
2. Range and proof in one sentence: startups through Oracle, the 3D platform that scaled 15 → 150 and was acquired, application security depth, Python as a core language.
3. How he works, where he is, and what he wants next: based in Barcelona, open to remote. Close with a direct, human invitation and the email as a link.

Cut: the four-paragraph life story, the generic teamwork paragraph, the degree summary (Education covers it).
Note: `description` (SEO) must be rewritten separately — 2–3 sentences, keyword-bearing, not a copy of About.

### 3.3 New section — "What I work with" (target: 5 lines)
Inserted directly after About. `layout: text`, one bolded line per area, no prose:

- **Languages:** Kotlin, Java (17+), Python, SQL
- **Backend:** Spring Boot, Quarkus, Kafka, REST, CQRS, microservices
- **Data:** PostgreSQL, MongoDB, Redis
- **Cloud & delivery:** AWS, Docker, Kubernetes, Terraform, CI/CD (GitHub Actions, GitLab CI, Jenkins, Bamboo)
- **Security:** application security, static analysis, vulnerability management (ASPM)
- **Leadership:** technical leadership, architecture, mentoring, cross-functional delivery

This is the ten-second keyword match for recruiters and ATS.

### 3.4 Projects (target: two case studies)
1. **Charlie — 3D render farm at Decora/CreativeDrive (flagship, ~350 words).** Now verifiable from press coverage, so use the sourced numbers instead of the vaguer CV phrasing: Decora was sold to CreativeDrive in March 2018 for **US$100 million**, the **second-largest Brazilian tech deal of 2018** after 99's sale to Didi Chuxing, after growing with no outside investment. Four short paragraphs: the pivot and the problem; what he architected (Java/Spring Boot, Python services for the render farm and automation, CQRS, microservices, MaxScript/3ds Max pipeline, quality checks); the scene composer in Unity; the outcome (15 → 150 people, the US$100M exit, clients including Target, Lowe's, Bed Bath & Beyond and Jacuzzi; CreativeDrive was later acquired by Accenture). End with a one-line stack. If "Charlie" was the product rather than the company, the heading must say so.
   - Cut the memoir framing ("Back in March 2016…"), the Uber analogy, the repeated "what I'm proud of" lines, and the personal reflection paragraph. Keep warmth through specifics, not reflection.
2. **Phoenix Security — ASPM platform (~150 words).** What the product does in one sentence, what he owned (design and delivery of the platform), the stack (Spring Boot, Kotlin, Java 17, Angular, PostgreSQL), and why it matters (security depth, current market relevance).
   - Marked as my call; swap for Hive or Channel if he prefers.

### 3.5 Experience (target: 10 roles, 60–90 words each)
Same shape for every entry:

> **One-sentence outcome as the `quote`** — e.g. "Rebuilt heat-cost billing as a real-time service, replacing manual utility processes across German buildings."
> Context in one clause → what he owned → one or two outcomes → `**Stack:** …`

- Repurpose `quote` from company marketing to a personal highlight. This gives every role a visible one-line win.
- Remove all company blurbs and the "Key Responsibilities" bullet list (Phoenix); responsibilities are implied by outcomes.
- Fix the tense and the title mismatch at Oracle ("Senior Application Security Engineer" vs "As an Application Security Engineer").
- beyonnex 2023–2024 and 2025–present are the **same project, two stints**, separated by his year at Phoenix. Write them as distinct chapters without repeating the product description: the first covers the initial build of the real-time heat-cost platform; the current one opens with the return ("After a year at Phoenix, I came back to the same platform") and covers what he owns now. One mention of the return, no duplicate paragraphs.
- FREE NOW is short and honest; keep it to three lines.
- Reticomm (CTO) and JExperts (lead) foreground ownership and team size, not tool lists. The Reticomm CTO role ran in parallel with CreativeDrive — both full-time, overlapping 24 months. Keep both date ranges and describe Reticomm as a concurrent leadership engagement rather than hiding it.
- HMW and Softplan are old and small; two or three lines each is enough. Do not pad them.
- The CV shows a **24-month overlap** between CreativeDrive (Mar 2016–Nov 2019) and Reticomm (Oct 2016–Oct 2018), not six months. If the CTO role was concurrent, fractional, or a side engagement, say so in the entry and keep the dates; if it was not, one set of dates is wrong and must be corrected.

### 3.6 Education (target: 2 lines each)
- Drop the university marketing quotes (the SENAI paragraph is repeated three times; the UniSul ranking is irrelevant to a hiring manager).
- Keep: institution, credential, years, and one line on what it added — e.g. "Postgraduate specialisation in data science; the statistics and modelling behind the recommendation and pricing work."
- Fix "Engineer's degree" → "Postgraduate degree, Engineering in Data Science" (a lato sensu postgraduation; About can keep saying "two postgraduate degrees").
- Keep the technical foundation (Automation, Software Technology) because it explains the hardware/3D background.

### 3.7 A Little More About Me (target: 4 lines)
Rewrite the intro sentence, keep the list, trim to five items, and make the home lab line concrete: two Proxmox hosts (a Dell R820 and an Intel NUC) running Kubernetes, Kafka, PostgreSQL, GitLab, Harbor and Nexus, provisioned with Terraform and Ansible. That single line does more for an infrastructure-minded reader than the other hobbies combined.

### 3.8 Close
One short section or footer line: "If you're building something in Kotlin or Java and want someone who has taken it from prototype to production, email me — guilherme@damoreira.com.br." Make the address a link.

---

## 4. Confirmed, and optional numbers

**Confirmed:**
- beyonnex is one project across two stints; he left for Phoenix in January 2025 and returned in August 2025.
- Based in Barcelona, open to remote; a visible "open to work" line is fine.
- Reticomm CTO and CreativeDrive lead overlapped for 24 months, both full-time and in parallel; keep the dates, name it a concurrent engagement.
- Home lab: two Proxmox hosts (Dell R820 and Intel NUC), Terraform + Ansible, running Kubernetes, Kafka, PostgreSQL, GitLab, Harbor, Nexus, Redis and friends.
- Education: postgraduation in Engineering in Data Science.
- Decora: sold to CreativeDrive in March 2018 for US$100M, the second-largest Brazilian tech deal of 2018; no outside investment; CreativeDrive later acquired by Accenture. Sources: Exame (15 Mar 2018) and NeoFeed (21 Aug 2025).
- Toptal badge and "Top 3%" stay; page stays in English; `Senior` titles from the entry headers; Python is a core language, not tooling-only; TypeScript out.

**Optional numbers.** These would make specific lines stronger, but the plan works without them — I write the qualitative version and never invent:
1. **Oracle:** how many teams/applications did you cover, and did the static-analysis tooling cut review time or findings?
2. **FREE NOW:** driver-base or team size, anything measurable about the delivery.
3. **beyonnex:** what "real-time" means in numbers (meters, buildings, latency, volume) and your team size.
4. **Phoenix:** what you personally shipped in eight months, and team size.
5. **Reticomm:** team size, number of clients.
6. **JExperts:** team size, any scale figure for the Channel platform.

---

## 5. Execution plan

1. **Pass 1 — foundation.** Rewrite `description` (SEO), `about_content`, and `title`. Insert "What I work with". No other section touched.
2. **Pass 2 — Projects.** Rewrite Charlie to ~350 words and add the Phoenix case study.
3. **Pass 3 — current roles.** beyonnex 2025, Phoenix, beyonnex 2023, Oracle. Verify each against the facts supplied.
4. **Pass 4 — older roles.** FREE NOW, Reticomm, CreativeDrive, Nexxera, JExperts, HMW, Softplan.
5. **Pass 5 — Education and hobbies.**
6. **Pass 6 — close and contact.** CTA line, email link, footer.
7. **Pass 7 — verification.** Read the rendered page top to bottom; grep `_config.yml` for the ban list (`cutting-edge`, `responsible for`, `utilize`, `revolutionizing`, etc.); confirm no paragraph appears twice; confirm every role is past tense except beyonnex; check that Kotlin, Java, Spring Boot, Quarkus, Kafka and Python each appear in the top third of the page.

Each pass is reviewable on its own; I will show the new text for approval before moving on, or do all seven and hand you a single diff — your call.

---

## 6. Acceptance checklist

- [ ] No duplicated sentence or paragraph anywhere in `_config.yml`, including SEO vs About.
- [ ] No employer marketing copy; every quote is about him.
- [ ] Every role: outcome + ownership + stack line, consistent shape.
- [ ] Past tense everywhere except the current beyonnex role.
- [ ] Kotlin, Java, Spring Boot, Quarkus, Kafka, Python and security all visible within the first screen.
- [ ] At least six concrete numbers or named outcomes across the page (15 → 150, acquisition, Top 3%, etc.).
- [ ] Zero banned filler words.
- [ ] A visible email call to action near the top and at the close.
- [ ] Page reads in under seven minutes; no role over 90 words except the flagship case study.
- [ ] No fact appears that cannot be traced to the current CV or a confirmation from you.
