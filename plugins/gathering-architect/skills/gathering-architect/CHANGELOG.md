# gathering-architect — Evidence & Coaching Pass (v3)

Pass following a skill-creator evaluation (static review + behavioral test runs vs. the v2 baseline). Two targets: tighten the coaching behavior based on user feedback, and clean up the evidence file's citations.

## SKILL.md changes
- **Diagnose-first held firm under urgency, with sharper framing.** Added an explicit "Urgency is not a reason to skip this" block: acknowledge the deadline and *promise the deliverable*, then ask the one or two questions that change the shape of the event. Urgency means thinking it through for the audience fast, not skipping the thinking. (User directive; confirmed by test feedback that liked the diagnose-first response even under a hard deadline.)
- **Added "make each question earn its place"** guidance — diagnostic questions must be specific and tied to a decision, with concrete options in parentheses. Addresses a "this is fine / felt generic" note on the meetup case.
- **Added an honest gut-check instinct** (Phase 2 + instinct #7): a warm coach will name the uncomfortable possibility — including that the gathering may have served its purpose or shouldn't happen. Came directly from user feedback praising that move in the baseline.
- **Rewrote the evidence instinct (#6) and the in-text citation example** to point at credible, named, peer-reviewed sources (Freeman et al. 2014, PNAS) and to explicitly warn off blog/"learning pyramid" numbers.

## social-learning-evidence.md changes — removed discredited / unsourced statistics
- **Cut the NTL "learning pyramid" retention figures** (e.g. 28% vs. 69%) — origin untraceable, widely flagged as fabricated. Replaced with Freeman et al. 2014 (PNAS, 225 studies) as the citable active-learning evidence.
- **Cut the "90%+ vs. 3–15% cohort completion" and "71% of learners" figures** — sourced to vendor/marketing blogs (Learnopoly, Growth Engineering), not research. Kept the directional, mechanism-based claim (social accountability improves follow-through).
- **Removed over-precise, unsourced scaffolding effect sizes** (d = 0.866, g = 0.587) from prose and the summary table; kept scaffolding as "~0.8, direction solid / exact value soft."
- **Fixed the Hattie (2009) citation** (was mis-attributed to a journal review of the book).
- **Added a "NOT recommended as citations" section** naming the removed sources so they don't creep back in.

Rationale: SKILL.md routes Claude to this file specifically when a user needs evidence to convince a stakeholder — the exact moment a fabricated statistic does the most damage. Net effect: fewer numbers, all defensible.

---

# gathering-architect — Cuts Pass (v2)

This is **Pass 1 of 2** for the open-source release refactor. Pass 1 = cuts and consolidation. Pass 2 = bundled assets and scripts (separate working session).

## Net result

| | Before | After | Delta |
|---|---:|---:|---:|
| SKILL.md | 182 | 187 | +5 |
| community-frameworks.md | 2,239 | 1,413 | **−826** |
| facilitation-methods.md | 1,103 | 1,283 | +180 |
| facilitator-pain-points.md | 1,439 | 1,406 | −33 |
| hackathons-and-builds.md | 1,769 | 1,262 | **−507** |
| social-learning-evidence.md | 779 | 771 | −8 |
| references/README.md | — | 23 | +23 |
| **Skill bundle total** | **7,511** | **6,345** | **−1,166** |

Roughly 15.5% smaller. About 33KB of fat removed; ~5KB of structural pointers and an index added. Net: smaller and crisper, with each topic having a clear canonical home.

(The CHANGELOG.md itself is documentation, not part of the runtime bundle — not counted in the total above.)

## What changed and why

### 1. Archival metadata stripped from all five reference files

Each reference file opened with a draft block ("Research Date: March 12, 2026 / Depth: Drill / Status: COMPLETE / Word Count: 25,000+") and closed with a similar footer. Useful while drafting, useless at runtime, and not appropriate for an open-source release. Stripped from heads and tails; replaced opening lines with tight runtime-useful intros that name the file's purpose and any cross-file pointers.

### 2. Open Space Technology de-duplicated

The same method had two full treatments: ~75 lines in `facilitation-methods.md` and ~215 lines in `hackathons-and-builds.md`. Same Four Principles, same Law of Two Feet, same marketplace process — both files explained the method from scratch.

**Resolution:** `facilitation-methods.md` is the canonical home (Open Space is a facilitation method; unconferences are an event format that applies it). The hackathons file now opens its unconference section with a pointer to the methods file and keeps only the unconference-specific content: when the format works, real-world challenges getting the Law of Two Feet to function, and the BarCamp variant. About 143 lines saved.

### 3. CoP framework consolidation

`community-frameworks.md` was ~60% Communities of Practice content, with three of five primary frameworks being CoP-flavored (Wenger, Tacit, JRC).

- **Wenger** kept as the canonical CoP treatment (~530 lines). This is the foundational framework.
- **Tacit Maturity Model** compressed from ~307 lines to 58 (preserved the 4 stages, 7 assessment dimensions, how-to-run-an-assessment, and external pointer; dropped the per-stage repeated subsections that read like internal consulting collateral).
- **JRC Playbook** compressed from ~542 lines to 46 (preserved the 8 facets in a table, the two entry-point use cases, and pointers to the free EU publication; dropped the per-facet "Purpose / Key Questions / Components / Outputs" expansions, which read like enterprise policy documentation rather than gathering design).

Net: ~745 lines saved on this consolidation. Substance retained; bulk that didn't help gathering design removed.

### 4. Minimum Viable Community (MVC) moved

MVC appeared twice in `community-frameworks.md` — once inside Community Canvas (as a 9-question tool that supports the canvas) and again as its own "Framework 6." Both treatments described the same thing.

**Resolution:** MVC moved to `facilitation-methods.md` under planning tools, where it sits alongside IDOARRT, 15% Solutions, Wicked Questions, and Min Specs. It's a tactical instrument, not a major design framework. The Community Canvas section in `community-frameworks.md` now points to it; the "Framework 6" entry was replaced with a short pointer.

### 5. Accelerator/Fellowship section cut

The `hackathons-and-builds.md` file had an "Accelerator & Fellowship Program Design" section. Per your call, cut entirely — multi-month programs aren't gatherings, and keeping them blurred the skill's scope.

**Honesty note on the audit numbers:** the upstream review estimated this section at ~600 lines. The actual section was ~210 lines (1173–1384 in the source). Still worth cutting on scope grounds, but the savings are smaller than the audit suggested. Want me to revisit whether accelerators deserve a separate file in a future pass, I'm open to it.

### 6. AI Workshops section moved

"AI Workshops & Hands-On Learning" (~145 lines) was in `hackathons-and-builds.md`, but most of the content is general workshop design (problem context, tool walkthrough, guided practice, hands-on building, sharing & reflection) with AI-specific annotations. The pair/mob programming subsections similarly apply beyond AI.

**Resolution:** Moved to `facilitation-methods.md` as a new section "Workshop Design for Hands-On Learning" (renamed for honesty — most of the content isn't AI-specific). The AI assistance notes are preserved as subsections within pair and mob programming.

### 7. SKILL.md routing table tightened

The routing table now (a) lists actual methods/frameworks inside each file rather than just topic categories, and (b) explicitly names canonical homes for the three topics that previously had dedupe issues (Open Space, MVC, CoP). Added a `references/README.md` that serves as the map when someone opens the folder.

### 8. Anti-slop language pass

Light cleanup of the more obvious offenders against the SKILL.md ban list:
- `Foster informal interaction` → `Encourage informal interaction`
- `Foster one-on-one mentoring` → `Encourage one-on-one mentoring`
- `Empower sub-group leaders` → `Equip sub-group leaders`
- `Leverage Cohort Completion Advantage` → `Use the Cohort Completion Advantage`

**Honesty note on what was left alone:** Domain terms like "Member Journey & Transitions" (an actual Community Canvas theme name) and "customer journey mapping" (a standard design sprint term) were preserved — sanitizing framework terminology would corrupt the content. "Robust relationship" was kept as the statistical term. "Seamless transitions" was kept inside the DJ analogy in `facilitator-pain-points.md` because it's the analogy that does the work.

## What was kept intact

- **`facilitator-pain-points.md`** — the most distinctive piece of the skill, per the upstream audit. Light metadata strip only. Most other facilitation skills don't include a "what goes wrong" lens.
- **`social-learning-evidence.md`** — kept the dual coverage of CoP (Lave & Wenger theory in §1.3 and organizational evidence in §11.1). The angles differ (theory vs research evidence) and the dual treatment is justified.
- **Wenger CoP treatment** in `community-frameworks.md` — full treatment retained as the canonical CoP source.
- **Hackathon design and execution sections** — kept fully; this is the operational guide for the format the file is named after.

## Pass 2 — Assets (now landed)

The upstream audit's biggest point was that this skill shipped zero bundled assets. Pass 2 addressed that. Five assets are now in `v2/assets/`, each built as a workshop instrument (preamble + fillable fields + worked example + closing prompt) rather than a static document.

| Asset | Purpose | Notes |
|---|---|---|
| `mvc-worksheet.md` | 9-question MVC sprint, 30-45 min | Generic open-source; vanity-metric editorialization left in |
| `idoarrt-template.md` | 6-field meeting design tool | Hiring debrief worked example with role-based names |
| `run-of-show-template.md` | SET/HOLD/LAND agenda for 90 min+ sessions | AI workshop worked example, 3-hour shape; pre-event checklist included |
| `community-canvas-runner.md` | Workshop facilitator's guide for the full 17-theme Canvas | Workshop-runner format, not a poster reproduction — the canonical poster lives at community-canvas.org |
| `agenda-builder-prompt.md` | Structured prompt for AI-generated draft agendas | Replaced the originally proposed Python script (`scripts/agenda_builder.py`) with a prompt template, see note below |

### Format change on the agenda builder

The original CHANGELOG promised `scripts/agenda_builder.py`. We shipped `assets/agenda-builder-prompt.md` instead. Reasoning:
- The natural primitive for this skill is an AI conversation, not a Python execution. Most users of the skill won't want to install Python to plan a meeting.
- The prompt is more directly useful from inside the gathering-architect skill itself (the skill can use the prompt as a planning scaffold).
- The inputs section maps cleanly to interactive Python `input()` calls and the instructions section maps to a system prompt — so a script wrapper is easy to add later if there's demand.

Open to revisiting if you'd rather have an actual runnable script.

### What was deliberately *not* added

- **No Academy-branded variants** of the templates (no PRISM mention, no Academy voice). All five are clean-generic for the open-source release. A parallel `assets/academy/` set could come in a future pass once we know what Academy-specific framings actually earn their keep.
- **No fillable PDFs or docx versions.** Markdown source only — the skill can render into other formats on demand.
- **No facilitator scripts.** The worksheets assume a facilitator who knows how to time-box. If we hear from users that scripts would help, easy to add later.

## What's still TODO

- **Tighten or relocate `assets/run-of-show-template.md`'s risk register section.** It adds length; some users may want it as an optional appendix rather than inline.
- **Test the prompt builder against a real session.** The worked example inside `agenda-builder-prompt.md` is plausible but synthetic — running it against an actual upcoming session would surface gaps.
- **Pick a real upcoming Academy session and pressure-test the run-of-show template end-to-end.** Note where it bends.

## Working location

This pass landed in `CLAUDE Co-Work/gathering-architect/v2/`. The original research files in `gathering-architect/gathering-architect-research/` were left intact for diff/reference. To ship as a plugin, the `v2/` folder is the bundle source.
