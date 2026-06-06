# Contributing to Cinematic Emotion Lab

This document defines the expectations, standards, and scope for contributions
to the Cinematic Emotion Lab research repository.

---

## Research Program Context

The Cinematic Emotion Lab is an active, publication-track research program. The
repository is structured as a staged public research record, not an open-development
project. Most substantive research decisions - experimental design, annotation
methodology, modeling architecture, dataset curation - are made by the primary
researcher and are not open to external modification during the active research phase.

What the repository welcomes:

- **Technical contributions** to the public code infrastructure: feature extraction
  utilities, visualization code, notebook formatting, dependency management, CI setup.
- **Documentation contributions**: corrections, clarity improvements, translation.
- **Community engagement**: substantive discussion in GitHub Discussions, issue-based
  questions labeled `inquiry`, literature references, and methodological observations.
- **Reproducibility testing**: attempting to reproduce the public pipeline on your own
  audio material and reporting your findings.

What the repository does not accept:

- Changes to annotation schema field definitions or annotation protocol
- Changes to the research methodology documentation that alter research positioning
- Addition of audio files, datasets, or annotation data from external sources
  without prior coordination with the primary researcher
- Changes to embargoed content boundaries or disclosure timing
- Modifications to the LICENSE or CITATION.cff without the author's written approval

If you are uncertain whether a contribution is in scope, open an Issue with the
label `inquiry` before beginning work.

---

## Issue Labels

| Label | Use |
|-------|-----|
| `inquiry` | Questions about the research, methodology, or collaboration |
| `bug` | Reproducible errors in public code or notebooks |
| `discussion` | Methodological or theoretical observations |
| `documentation` | Errors or gaps in written documentation |
| `visualization` | Issues or improvements in visualization code |
| `infrastructure` | CI, dependencies, environment setup |

---

## Development Setup

**Python version:** 3.12 required. Python 3.13 is not supported (arm64 numpy
incompatibility on Apple Silicon).

```bash
git clone https://github.com/bernardvgosh/cinematic-emotion-lab.git
cd cinematic-emotion-lab
python3.12 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

All public notebooks are developed and tested on Python 3.12. If a notebook
fails to execute in this environment, open a bug issue.

---

## Code Standards

**Language:** Python 3.12
**Style:** PEP 8 with a 100-character line limit
**Type hints:** Required on all new public functions
**Docstrings:** Single-line only. Document the why, not the what.
**Comments:** Minimal. Only when the reasoning is non-obvious.

**Notebook standards:**
- Clear all cell outputs before committing (`Kernel > Restart & Clear Output`)
- Markdown cells must use institution-grade language — see terminology standards
  in [docs/PUBLIC_POSITIONING.md](docs/PUBLIC_POSITIONING.md)
- Each notebook must include the `cel_metadata` block in its kernel metadata
- Notebooks must auto-degrade gracefully when the real corpus is not present
  (synthetic demonstration path, clearly labeled)

---

## File Naming

Follow [NAMING_CONVENTIONS.md](NAMING_CONVENTIONS.md) strictly for all new files.

Key conventions:
- Notebooks: `NB-[TYPE]-[NNN]_[topic-slug]_[YYYY-MM-DD].ipynb`
- Research logs: `[NNN]-[topic-slug].md`
- Scripts: `[action-verb]-[target].py`
- Data files: `[dataset-id]_[descriptor]_[version].csv`

---

## Commit Standards

Follow [GIT_STANDARDS.md](GIT_STANDARDS.md) for all commits.

Format: `type(scope): description`

Approved types: `release`, `feat`, `data`, `docs`, `experiment`, `viz`, `refactor`, `fix`, `ci`, `infra`

Keep the description under 72 characters. Use the body for context where needed.
No attribution lines of any kind in commit messages.

---

## Pull Request Guidelines

- One logical change per PR. Keep scope narrow.
- Reference the Issue number the PR addresses (`Closes #NNN` or `Ref #NNN`).
- Include a concise description of what changed and why.
- All notebooks must have cleared outputs.
- All Python files must pass `pycodestyle` at the configured line limit.
- Maintainer review is required before merge. Review may take up to two weeks
  during active research phases.

---

## Language and Tone Standards

All written contributions to documentation, notebook markdown cells, and research
logs must use the terminology and register defined in
[docs/PUBLIC_POSITIONING.md](docs/PUBLIC_POSITIONING.md).

Key requirements:
- Use "cinematic audio cues" not "clips"
- Use "composer annotations" not "labels"
- Use "embargoed" not "hidden" or "unavailable"
- Do not use "my research" — use "this research" or "this research program"
- Do not speculate about results or findings in documentation
- Do not use student-project language ("I tried to", "hopefully", "might work")

If you are uncertain about register, read the existing documentation and
match it.

---

## Data and IP Notice

Do not commit audio files, proprietary datasets, or any material that is not
your own original work or is not under a license compatible with this repository.

The annotation corpus and all associated labels are proprietary to this research
program. Do not attempt to reconstruct, reverse-engineer, or publish data derived
from the public feature subset in a way that circumvents the publication embargo.

See [docs/ip-and-disclosure-notice.md](docs/ip-and-disclosure-notice.md) for the
full intellectual property and data disclosure policy.

---

## Code of Conduct

All contributors are expected to adhere to the
[Code of Conduct](CODE_OF_CONDUCT.md). The standards there apply to Issues,
Pull Requests, Discussions, and any other form of engagement with this repository.

---

## Questions and Collaboration Inquiries

For general questions about the research: open an Issue labeled `inquiry`.

For collaboration, research partnership, or academic engagement inquiries:
contact the primary researcher at contactbernardg@gmail.com with the subject
line `[Cinematic Emotion Lab] Collaboration Inquiry`.

---

*Cinematic Emotion Lab - Contributing Guide v2.0 - 2026*
