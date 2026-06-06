# GitHub Pages & Update Strategy
## Cinematic Emotion Lab · Public Presence Guide

---

## GitHub Pages Structure

When GitHub Pages is activated for this repository, the recommended structure is:

```
cinematic-emotion-lab/
└── docs/
    └── index.html (or _config.yml for Jekyll)
```

Or use a dedicated `gh-pages` branch for a fully custom site.

### Recommended Page Hierarchy

```
/ (index)              — Lab overview, mission, current status
/research              — Research questions, methodology summary
/experiments           — EXP index with status indicators
/visualizations        — Gallery of published visualizations
/team                  — Author bio + collaborators
/publications          — Papers, preprints, citations
/updates               — Research log / changelog feed
```

### Jekyll Theme Recommendation

Use a minimal dark theme — no pre-built academic themes. Custom CSS matching the lab's Noir Intelligence visual system. Key CSS variables:

```css
:root {
  --bg:       #08080C;
  --surface:  #12121C;
  --accent:   #DC2D46;   /* tension crimson */
  --amber:    #F5A623;
  --ice:      #4FC3F7;
  --text:     #E8E8F0;
  --muted:    #505069;
  --mono:     'IBM Plex Mono', monospace;
  --serif:    'Gloock', Georgia, serif;
}
```

---

## README Badge Strategy

Add these badges immediately below the banner image in the README:

```markdown
![Status](https://img.shields.io/badge/Status-Active_Research-DC2D46?style=flat-square&labelColor=08080C)
![Phase](https://img.shields.io/badge/Phase-Feature_Extraction-F5A623?style=flat-square&labelColor=08080C)
![Python](https://img.shields.io/badge/Python-3.10+-4FC3F7?style=flat-square&logo=python&labelColor=08080C)
![Framework](https://img.shields.io/badge/Framework-librosa_·_PyTorch-A8E6CF?style=flat-square&labelColor=08080C)
![License](https://img.shields.io/badge/License-MIT-505069?style=flat-square&labelColor=08080C)
![Domain](https://img.shields.io/badge/Domain-Computational_Musicology-A778E6?style=flat-square&labelColor=08080C)
```

Update the `Phase` badge with each release:
- `Feature_Extraction` → `Dataset_Construction` → `Baseline_Results` → `Publication_Pending`

---

## Iconography Suggestions

Use Unicode and simple SVG glyphs in docs and README tables — no emoji, no icon libraries. Suggested symbols for the lab's visual language:

| Symbol | Use |
|--------|-----|
| `◈` | Experiment marker |
| `∿` | Waveform / audio |
| `▦` | Feature matrix / data |
| `◉` | Target / output |
| `⟳` | In progress |
| `✓` | Complete |
| `⌀` | Null / withheld |
| `→` | Pipeline flow |
| `·` | List separator |
| `//` | Section divider in labels |

---

## Weekly GitHub Update Strategy

### Activity Signal Cadence

GitHub's contribution graph is a public credibility signal. The following minimum cadence maintains a consistent presence:

**Weekly (every week without exception):**
- Commit a new `WEEK-XX_YYYY-MM-DD_research-log.md`
- Even if the content is brief — one observation, one blocked question, one result that didn't work

**Bi-weekly:**
- A new or updated visualization in `visualizations/plots/`
- A script update or new utility in `scripts/`

**Monthly:**
- Update README status bars
- Add a new entry to `UPCOMING_RELEASES.md`
- A notebook update — even a minor cell refinement

**Quarterly:**
- Stage release (per `RESEARCH_STRATEGY.md`)
- Update `RESEARCH_QUESTIONS.md` with any refinements
- Archive completed research logs to `research-notes/`

### Commit Message Tone

Every commit should read like a research decision, not a development task:

```
[LOG] week-03: annotation framework finalized, edge cases documented
[VIZ] plots: add spectral centroid over time for INC001 tension cue
[DATA] annotations: complete pass 1 on 24 clips, 6 flagged for re-annotation
[NB] eda-001: add feature distribution section, ZCR analysis added
[DOCS] research-questions: refine RQ-03 framing based on annotation observations
```

Never: `update readme`, `fix stuff`, `minor changes`, `wip`

---

## Research Log Strategy

Weekly logs are a public signal of research activity and intellectual honesty. They should feel like field notes from a serious research practice — not polished reports, but not casual either.

### Log Structure

Each log follows `RESEARCH_LOG_TEMPLATE.md` with these priorities:

1. **What was observed** — factual, specific, no interpretation yet
2. **What was unexpected** — this is gold; note it immediately
3. **What blocked progress** — intellectual honesty is a credibility signal
4. **What changed in the model** (methodology, not code)
5. **Composer intuition notes** — observations that resist formalization

### Public-Safe Log Language

Observations that can be published without disclosing findings:

> "Annotation pass on 8 clips revealed consistent disagreement on the tension/suspense boundary. Refining schema."

> "ZCR analysis surfaced an unexpected outlier cluster. Investigating whether it represents a genre effect or an annotation artifact."

> "Tempo estimation fails on rubato passages. Documented as a known limitation. Investigating manual BPM annotation for affected clips."

> "HPSS separation is less clean on dense orchestral textures than on chamber textures. Feature reliability varies by orchestration density."

---

## Suggested Diagram Creation Roadmap

### Immediate (create now)
- Emotion category taxonomy tree (hierarchical: primary → secondary → edge cases)
- Annotation schema field diagram (visual representation of the JSON schema)
- Feature extraction signal chain (full flowchart, component-level)

### Q3 2026
- Temporal emotion arc diagram (abstract, no real data — illustrative)
- Composer annotation workflow diagram
- Acoustic feature correlation concept map

### Q4 2026
- Model architecture comparison table (visual, not code)
- Composer Gap conceptual diagram (Venn: acoustic space vs. compositional intent space)
- Narrative position × emotion category matrix (heatmap-style, values withheld)

---

*Last updated: 2026-06-06*
