# Agenda Builder Prompt

A structured prompt template for generating a first-draft agenda from a small set of inputs. Hand the filled-in version to Claude, ChatGPT, or any capable AI assistant and you'll get a draft agenda mapped to the SET / HOLD / LAND arc, with method recommendations and energy notes.

> **Why this is a prompt, not a script:** The CHANGELOG originally proposed `scripts/agenda_builder.py`. We chose a prompt template instead because the natural primitive for this skill is an AI conversation, not a code execution — and because most users of this skill don't want to install Python to plan a meeting. If you want a script too, the inputs section below maps cleanly to interactive `input()` calls; the instructions section maps to a system prompt for a small LLM wrapper. Easy to build later if there's demand.

---

## How to use this prompt

1. Fill in the **Inputs** section below with your context. Skip what doesn't apply.
2. Copy the **Inputs** and **Instructions to the AI** sections into your AI of choice. Send.
3. The AI returns a draft agenda. Treat it as a first draft, not a final plan. Iterate.
4. Once you like the draft, export it into the run-of-show template (`run-of-show-template.md`) for the operational version.

### When this prompt is useful
- You have less than 10 minutes to design something and need a real starting point
- You're stuck on a design and want a counter-proposal to react to
- A co-facilitator is asking "what's the plan" and you need a sketch fast
- You want to compare two different shapes for the same session

### When this prompt is the wrong tool
- You haven't done the diagnostic work yet (purpose, audience). Run the diagnostic first — see the SKILL.md coaching flow.
- You're running something brand-new with high stakes and unfamiliar group dynamics. Co-design with a human facilitator.
- The session is shorter than 45 minutes. Use IDOARRT instead.

---

## INPUTS — Fill these in

### 1. Purpose (one or two sentences)
> What's this session actually for? Not the category — the underlying outcome. Example: "Help 25 mid-career professionals feel they can use AI tools at work without permission."

**Your purpose:**

---

### 2. Desired outcomes (2–4 concrete walkaways)
> What should each participant walk away with? Be specific.

**Outcome 1:**

**Outcome 2:**

**Outcome 3 (optional):**

**Outcome 4 (optional):**

---

### 3. Audience
> Who's in the room? Number of people, their experience level, do they know each other, what's the power dynamic. Example: "20 participants, mid-career, mostly don't know each other, mixed seniority but no direct reporting lines."

**Your audience:**

---

### 4. Duration and format
> How long, in-person or virtual or hybrid, what's the physical or digital setup.

**Duration:**

**Format:**

**Setup notes:** (e.g., "U-shape seating possible," "no whiteboard," "60% on Zoom from EU timezones")

---

### 5. Vibe
> How should this feel? Pick a few words. Examples: "buzzy and high-energy," "reflective and intimate," "challenging and brave," "warm and grounded."

**Your vibe:**

---

### 6. Constraints
> What can't move? Hard timing constraints, banned topics, accessibility needs, language requirements, anything that would shape the design.

**Your constraints:**

---

### 7. Risk to design around (optional but useful)
> What's the most likely thing to go wrong, given your audience? Example: "One senior person will try to dominate." Example: "Half the room will say they have no AI experience even though they do."

**Your risk:**

---

### 8. Special requests (optional)
> Anything specific you want the AI to consider. Example: "Use Liberating Structures methods preferentially." Example: "Build for a co-facilitator who's running it without me."

**Your requests:**

---

## INSTRUCTIONS TO THE AI

Paste everything above into the AI, then add the instructions below.

---

You are an experienced facilitator helping design a gathering. Using the inputs above, produce a draft agenda following these rules:

1. **Start with purpose, not activities.** Open the response by reflecting back the purpose in your own words, in one sentence. If the purpose feels weak or category-shaped (e.g., "have a team meeting"), name that gently and propose a stronger framing before continuing.

2. **Structure the agenda using the SET / HOLD / LAND arc:**
   - **SET** (typically 15–25% of total time): Open with connection, name purpose, surface what's in the room. Lower the entry barrier for introverts and newcomers.
   - **HOLD** (typically 60–70%): Productive challenge, content, real work. The middle is where the design earns its keep.
   - **LAND** (typically 15–25%): Reflection, integration, commitment. Build the LAND first, not last — if HOLD runs over, LAND is what gets squeezed.

3. **Recommend specific facilitation methods, not generic activities.** Don't say "icebreaker" — say "Impromptu Networking, 15 minutes, pairs rotate every 3 minutes around the question..." Use methods from Liberating Structures, Open Space, World Café, 1-2-4-All, Fishbowl, IDOARRT, Marshmallow Challenge, Human Spectrogram, Mastermind, or others as appropriate. Match the method to the group size and vibe.

4. **Annotate energy.** For each block, mark the intended energy in parentheses: (social), (settling), (focused), (productive struggle), (buzzy), (reflective), (warm close), etc. Read the column down at the end — if you see three high-energy blocks in a row, redesign.

5. **Design for introverts by default.** Include processing time (silent writing before share), small-group options before plenary, and writing-as-thinking patterns. Half the room needs this and won't ask.

6. **Be honest about transitions.** For any transition longer than 2 minutes, name how you'll bridge it (energizer, reflective pause, movement, change of pace).

7. **Surface the most likely failure mode** at the end. One sentence: "The thing most likely to go wrong with this design is..." This is more useful than a polished closing.

8. **Don't hide trade-offs.** If you cut something, say what you cut and why. If two activities both fit and you picked one, say why.

### Expected output format

```
**Purpose (reflected):** [Your one-sentence reflection]

**Total duration:** [from inputs]
**Energy arc:** [a short text arc, e.g., "social → focused → productive struggle → reflective"]

### SET ([X] min)

| Time | Block | Activity | Why this | Energy |
|------|-------|----------|----------|--------|
| 0:00–0:XX | [name] | [method, with brief instructions] | [why it fits the purpose / audience / vibe] | [energy word] |
[...]

### HOLD ([X] min)

[same table format]

### LAND ([X] min)

[same table format]

### Trade-offs
- Cut: [what you considered but didn't include, and why]
- Risk: [the most likely failure mode in one sentence]
- Alternative: [one alternative shape for this same purpose, briefly described]
```

---

## A worked example

**Filled inputs:**

> 1. Purpose: Give 20 mid-career marketing professionals their first concrete experience using AI tools for a real work task, and the confidence to try one new thing at work this week.
>
> 2. Outcomes: (a) Each person ships one working prototype using an AI tool. (b) Each person leaves with one named, scoped commitment for the week. (c) Enough trust in the room that people will share what didn't work, not just what did.
>
> 3. Audience: 20 people, mid-career, mostly don't know each other, mixed industries, mostly self-rate as "AI-curious but not confident."
>
> 4. Duration and format: 3 hours, in-person, U-shape seating possible, whiteboard available.
>
> 5. Vibe: Buzzy at first, focused in the middle, warm close. Not preachy.
>
> 6. Constraints: Some participants may not have laptops; need to plan for shared screens. Mixed AI-tool fluency from "never used one" to "build with them weekly."
>
> 7. Risk: One or two people in the room will be much more advanced than the rest, and may either dominate or check out.
>
> 8. Special requests: Use Liberating Structures methods where possible.

**Output the AI should produce:**

> **Purpose (reflected):** Give 20 mid-career marketers their first shipped AI prototype and a Monday-morning commitment to keep going.
>
> **Total duration:** 180 min
> **Energy arc:** social → settling → buzzy → focused → productive struggle → relief → reflective
>
> ### SET (45 min)
>
> | Time | Block | Activity | Why this | Energy |
> |------|-------|----------|----------|--------|
> | 0:00–0:10 | Arrival | Music, name tags, coffee, casual mingling | Lower entry barrier; signal informality | Social |
> | 0:10–0:20 | Welcome + frame | Lead names purpose; surfaces range ("who's been doing this 6+ months / 6+ days / never") to honor all skill levels | Defuses the dominance/check-out risk by making the spread visible and acceptable | Settling |
> | 0:20–0:45 | Impromptu Networking (Liberating Structures) | Pairs rotate every 3 min around "what's one thing AI surprised you with, or what's one thing you wish it could do for you?" | Lowers stakes, generates buzz, surfaces real questions before content starts | Buzzy |
>
> ### HOLD (110 min)
>
> [...detailed blocks for demo, guided practice, independent build, pair Show & Tell...]
>
> ### LAND (25 min)
>
> [...blocks for whole-room highlights, 15% Solutions commitment round, closing circle...]
>
> ### Trade-offs
> - Cut: A second skills-deep block in the middle. Decided one shipped prototype with reflection beats two half-done ones.
> - Risk: The advanced participants either dominate the demo or disengage during guided practice. Mitigation: pair them with newcomers in the build block as informal mentors — a role, not a label.
> - Alternative: If the group skews more advanced than expected, swap the Demo + Guided Practice (25 min) for a single Open Space-style block where pairs self-organize around real use cases. Higher variance, higher potential.

---

**Sources:**
- Run-of-show structure: `run-of-show-template.md`
- Method catalog: `references/facilitation-methods.md`
- Failure modes: `references/facilitator-pain-points.md`
