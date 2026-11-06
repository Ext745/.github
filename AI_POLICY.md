# AI Usage Policy

Applies to all repositories under [Ext745](https://github.com/Ext745) unless a repo says otherwise.

## How my projects are built
They're developed with large language models (primarily Claude, via Claude Code). The models are used for research, design exploration, code generation, refactoring, and documentation. The approach is described in [APPROACH.md](APPROACH.md).

## What that means for you
- **A human owns everything here.** I direct the work and I'm responsible for every commit, however it was produced.
- **Real hardware decides what works.** Nothing is marked verified because it compiles, passes unit tests, or because an AI said so. Verification means running on the actual target hardware, logged in each repo's `TESTING.md`.
- **State is stated honestly.** `STATUS.md` and the maturity label in each README say what's verified, what's experimental, and what's abandoned.
- **Provenance.** AI-assisted commits carry a `Co-Authored-By` trailer, and `STATUS.md` records which model or tool did each session.
- **Copyright.** Code is released under each repo's LICENSE, to the extent copyright applies. The legal status of AI-generated material is unsettled in several jurisdictions; my human direction, selection and editing are part of every project.

## Contributions
AI-assisted contributions are welcome, under these conditions:
1. Disclose AI use in the PR or issue description (the templates ask).
2. You've read, built, and tested what you submit. Say what hardware you tested on, if any. Untested AI output will be closed.
3. Keep PRs focused: one change, explained in your own words.
4. Bug reports must be reproduced by you. No unverified AI-generated vulnerability reports.

## My conduct in other projects
I respect each project's stance on AI. I don't submit AI-assisted PRs, issues, or reports to projects that prohibit them. Where a project has no stated policy, I disclose AI use up front or ask first. I never point automated agents at other people's repositories without permission.
