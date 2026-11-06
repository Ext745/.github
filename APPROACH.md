# Development Approach

## The stance
I publish everything: working code, failed attempts, and raw AI output, because the process is as valuable as the result. Nothing here is hidden or polished for appearance. What *is* guaranteed is honesty about state: every part is labelled as verified, experimental, or abandoned. If you'd prefer a summary, point your AI at the repo. It's structured so an AI can read it correctly.

## AI-led, human-directed
I define the goal, constraints, and acceptance criteria. LLM agents do much of the design exploration and implementation. This lets a project reach further than my own expertise alone would allow, and it regularly produces approaches I wouldn't have chosen myself. Several of my projects exist only because of that.

What keeps it honest, in every repo:
- **Origin and intent:** `GOAL.md` and `docs/origin.md`
- **Decisions and rationale:** `docs/decisions/`
- **Current state:** `STATUS.md`, including which model or tool did each session
- **Raw exploration:** `lab/`, kept, visible, and marked unverified

## Real hardware, real time
I consider this the biggest strength of this work.

Code doesn't count as working because it compiles, passes unit tests, or because an AI says it does. It counts as working once it has **run on the actual target hardware** (the radio, SDR, microcontroller, amplifier, or host it was written for) **for extended periods: hours, then days, then weeks.**

Long runs on real hardware catch what short tests and simulations never will:
- thermal drift and heat-related failures
- memory leaks and resource exhaustion
- USB, driver, and firmware resets
- timing races and rare edge cases
- RF interaction, noise, and power events
- the gap between "works on the bench once" and "keeps working"

Every run is recorded by a soak logger and listed in the repo's `TESTING.md` with hardware, commit, configuration, duration, and result, plus the raw time-series data in `tests/soak/logs/`. The claim can be checked, not just asserted.

## Maturity levels
| Label | Meaning |
|---|---|
| `experimental` | Written; may not build; not run on target hardware |
| `bench-tested` | Runs on real target hardware in short sessions |
| `soak-tested` | Continuous real-hardware runtime (hours → weeks), logged in TESTING.md |
| `stable` | Soak-tested, in regular use, no open critical issues |
| `abandoned` | Kept for reference; don't build on it |

Only I set a level above `experimental`, and only on the basis of logged hardware runs. Releases are tagged at each new level, and the release notes list the runs behind them.

## Workflow
1. **Idea → prior-art research.** Findings recorded in `docs/origin.md`.
2. **Go / no-go.**
3. **Start from the project template.**
4. **Write GOAL.md:** goal, constraints, non-goals, acceptance criteria, reference links.
5. **Agent-led exploration with human steering.** The agent keeps STATUS.md current and records direction changes as decisions.
6. **Verification gates:** automated tests (CI), then real-hardware runs, then long-duration soak.
7. **Publish with an honest maturity label.**

Most repos start private and go public later. Secret and personal-data scanning runs from the first commit regardless, because history goes public with the repo.

## Safety
Some projects involve high voltage, RF power, or stored energy. AI-proposed changes in those areas are checked against datasheets and established references before they touch hardware. If you build anything from these repos, especially from `lab/`, you're responsible for your own safety review and for legal operation in your jurisdiction.
