# Staged Release Strategy
## Cinematic Emotion Lab - Public Disclosure Framework

> This document governs how, when, and in what language the Cinematic Emotion Lab
> releases research artifacts to the public. It is a strategic instrument, not a
> calendar. Every release decision is made against a single criterion: does this
> advance intellectual momentum without disclosing findings prematurely?

---

## Strategic Premise

The research is substantially complete. What is being managed is not a research
timeline - it is a disclosure architecture. The work exists. The question is how
to surface it in a sequence that builds credibility, sustains curiosity, and
positions this work correctly before formal publication.

The goal is not to create hype. The goal is to create **deserved attention** through
a structured, honest public record of a serious research program.

This framework has three design principles:

1. **Methodology before results** - Disclose the how before the what.
2. **Architecture before performance** - Show the system before the numbers.
3. **Framing before findings** - Establish the theoretical stakes before surfacing evidence.

---

## Disclosure Layers

Research artifacts fall into one of four disclosure categories:

### Layer A - Immediately Disclosable
Infrastructure, methodology, and theoretical framing. No competitive risk.
No publication embargo.

Examples:
- Research philosophy and experimental design documentation
- Feature extraction pipelines (code, not results)
- Annotation schema and protocol documentation
- Visual identity and research communication assets
- Architecture diagrams and system documentation

### Layer B - Disclosable with Framing
Partial results, qualitative characterizations, structural findings.
Requires deliberate framing language to withhold precision.

Examples:
- Qualitative classification results ("separability observed" without accuracy figures)
- UMAP feature space projections (clusters visible, labels withheld)
- Visualization suites without interpretive conclusions
- Feature importance rankings (relative, not absolute)

### Layer C - Embargoed Pending Publication
Quantitative results, trained model weights, full annotated dataset.
Not released until publication timeline is confirmed.

Examples:
- Per-class accuracy and F1 metrics from EXP-002
- Trained model weights and evaluation artifacts
- Full composer annotation corpus
- Quantitative Composer Gap divergence metrics

### Layer D - Permanently Withheld or Delayed
Materials that could be replicated to undermine novelty before publication,
or that contain identifiable compositional material.

Examples:
- Raw audio files (composer IP protection)
- Specific chord/harmonic sequence transcriptions
- Final theoretical conclusions before preprint

---

## Release Sequencing Logic

Each public release is designed to answer a specific question in the
audience's mind - and to leave a more significant question unanswered.

| Release | Answers | Leaves Open |
|---------|---------|-------------|
| v0.1 | "Is this a serious research program?" | "What has it found?" |
| v0.15 | "Does the feature space have structure?" | "How separable is it?" |
| v0.2 | "Is the ground truth real and rigorous?" | "What do the labels reveal?" |
| v0.25 | "How is compositional intent encoded?" | "Does the machine understand it?" |
| v0.3 | "Can the machine classify cinematic emotion?" | "How well? By how much?" |
| v0.35 | "Can tension be modeled over time?" | "What do the trajectories reveal?" |
| v0.4 | "Where does the machine diverge from the composer?" | "By how much, and why?" |
| v0.5 | "Can this be experienced interactively?" | "What does the full dataset show?" |
| v1.0 | Everything. | (Publication is the answer.) |

---

## Language Architecture

### What to Say and What to Withhold

**When results exist but are embargoed:**
> "Initial experiments establish statistically significant separability across
> annotated emotion categories. Quantitative characterization is withheld
> pending peer-reviewed publication."

**When the corpus exists but full details are withheld:**
> "The research corpus includes a professionally annotated collection of
> cinematic audio cues. A curated public subset is available for community
> engagement. Full dataset release is timed to publication."

**When the model works but performance metrics are withheld:**
> "Baseline classification demonstrates feasibility of the cinematic emotion
> recognition task within this feature space. Per-class performance metrics
> are embargoed."

**When the Composer Gap study is referenced before full disclosure:**
> "Early interpretive analysis has begun to surface a structured divergence
> between machine predictions and composer-annotated intent. The taxonomy of
> this divergence is under active investigation."

**When asked about a timeline:**
> "The research is proceeding according to a staged disclosure schedule.
> The next public release is planned for [month]. Significant findings will
> be disclosed through formal publication channels."

---

## Announcement Architecture

Each release follows a three-part announcement structure:

**1. GitHub commit message** (under 72 chars)
Terse, artifact-first, no superlatives.
Format: `release(vX.X): [artifact name] - [one-line description]`

**2. Repository release notes** (100-300 words)
State what is being released, what it signals, what remains withheld.
No speculation. No hedging. Confident and specific.

**3. LinkedIn post** (see docs/LINKEDIN_RELEASE_ANGLES.md)
Written for AI research, film industry, and academic audiences simultaneously.
Each release has a distinct angle - not a repetition of the commit message.

---

## Audience-Specific Framing

The research speaks to three distinct audiences. Language must serve all three
simultaneously.

### AI/ML Research Community
Emphasis: methodological rigor, feature engineering decisions, model architecture choices.
Signal: this is not a demo project - it has a defined research question, experimental
protocol, and embargo-protected results.

Key phrases:
- "71-dimensional acoustic feature space"
- "composer-annotated ground truth"
- "staged disclosure pending peer review"
- "statistically significant separability"

### Film Industry / Music Community
Emphasis: the central research problem and its creative stakes.
Signal: this is not academic abstraction - it investigates something that matters
to anyone who has ever scored a film or watched one.

Key phrases:
- "compositional intent vs. machine perception"
- "the gap between what a composer writes and what the algorithm hears"
- "emotional architecture of film scoring"
- "the Composer Gap"

### Academic / Research Recruitment
Emphasis: interdisciplinary position, publication trajectory, research governance.
Signal: this is a structured, documented research program with a clear path to
publication and a genuinely novel theoretical contribution.

Key phrases:
- "interdisciplinary research at the intersection of MIR and affective computing"
- "publication-track research program"
- "novel ground truth methodology: compositional intent as annotation target"
- "staged public disclosure framework"

---

## Momentum Maintenance Protocol

Between formal releases, the following maintain public research presence
without disclosing protected findings:

**Weekly research logs** - Committed to `research-logs/` every 7-14 days.
Written in public-safe language. Demonstrate active research cadence.

**Visualization drips** - Individual analysis figures released to `visualizations/`
without interpretive framing. Let the images create questions.

**Documentation updates** - Progressive enrichment of methodology and
architecture documentation signals ongoing research depth.

**Issue engagement** - Thoughtful responses to GitHub issues labeled `inquiry`
demonstrate research seriousness and build community.

---

## Embargo Breach Protocol

If findings are discussed publicly before formal release - in conversation,
conference presentation, or social media - the following language governs:

> "This research is part of an active publication-track program. Results
> referenced here are preliminary and are subject to revision before formal
> disclosure. For the official record, please follow the staged release
> schedule at the repository."

This is not a retraction. It is a positioning statement that reinforces
the publication-track framing.

---

*Cinematic Emotion Lab - Staged Release Strategy v1.0 - June 2026*
