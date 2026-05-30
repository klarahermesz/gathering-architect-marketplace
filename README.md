# Gathering Architect

A coaching-first Claude skill for designing gatherings that actually connect people: workshops, meetups, hackathons, team sessions, and learning communities. It draws on facilitation science, community design frameworks, and social-learning research to go well beyond "make an agenda."

Distributed as a Claude Code / Cowork **plugin marketplace** containing one plugin (`gathering-architect`), which provides the skill.

## What the skill does

Instead of immediately spitting out a schedule, it works like a good facilitator would:

- **Diagnoses purpose first.** It asks two or three sharp questions before recommending anything, because every other decision flows from why you're gathering. Even under time pressure, it promises the deliverable and still asks the questions that change the shape of the event.
- **Recommends the non-obvious.** Specific methods with reasoning (World Café, Impromptu Networking, 1-2-4-All, Fishbowl, Open Space) rather than generic "do an icebreaker."
- **Designs for introverts by default.** Processing time, small-group options, write-before-speak patterns.
- **Thinks in energy, not just time.** Uses a SET / HOLD / LAND arc to sequence activities.
- **Names what can go wrong**, and offers an honest gut-check, including whether a gathering should happen at all.
- **Backs claims with defensible evidence** (named, peer-reviewed sources), not blog statistics.

It bundles five reference libraries (facilitation methods, community frameworks, hackathon/build formats, social-learning evidence, facilitator pain points) and five ready-to-use templates (MVC worksheet, IDOARRT, run-of-show, Community Canvas runner, agenda-builder prompt).

## Install

In Claude Code (or Cowork), add this marketplace and install the plugin:

```
/plugin marketplace add klarahermesz/gathering-architect
/plugin install gathering-architect@gathering-architect
```

Then just describe a gathering you're planning, or run the skill directly:

```
/gathering-architect:gathering-architect
```

## Add it to Cowork (no coding needed)

Using the Claude desktop app instead of the terminal? You can add this without any commands:

1. Download **`gathering-architect-cowork-plugin.zip`** from this repo (click the file in the list above, then the **Download raw file** button). You'll need a paid Claude plan (Pro, Max, Team, or Enterprise).
2. Open the **Claude desktop app** and click the **Cowork** tab.
3. In the left sidebar, click **Customize** — this is where your skills and plugins live.
4. Choose **Add plugin** (or "Browse plugins"), then **Upload a file**, and select the zip you downloaded.
5. Start a Cowork chat, type **/** and pick **gathering-architect** — or just describe the event you're planning and Claude will reach for it.

(Menu labels in Cowork shift slightly between versions, but the path is always through **Customize**.)

## What's inside

```
.claude-plugin/marketplace.json          the marketplace catalog
plugins/gathering-architect/
  .claude-plugin/plugin.json             the plugin manifest
  skills/gathering-architect/
    SKILL.md                             the skill itself
    references/                          five on-demand reference libraries
    assets/                              five workshop templates
    CHANGELOG.md                         version history
```

## License

Licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — use and adapt it freely, including commercially, as long as you credit Klara Hermesz and link the license. See [`LICENSE`](LICENSE).

The skill references third-party frameworks ([Community Canvas](https://community-canvas.org), [Liberating Structures](https://www.liberatingstructures.com), Wenger's Communities of Practice, and others). Those are owned by their respective authors and cited as references; this license covers the original writing and synthesis of the skill.

## Credits

Created by **[Klara Hermesz](https://github.com/klarahermesz)**, Co-founder & Chief Learning Architect at [AI Enablement Academy](https://aienablement.academy).
