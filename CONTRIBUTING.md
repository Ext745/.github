# Contributing

Thanks for your interest. Contributions are welcome, including AI-assisted ones.

**Before you start, read the [AI usage policy](AI_POLICY.md).** In short:
1. Disclose AI use.
2. Build and test what you submit, and say what hardware you tested on, if any.
3. One focused change per PR, explained in your own words.
4. Reproduce bugs yourself before reporting them.

## How
- **Bugs:** open an issue using the bug template. Include hardware, OS/firmware, commit, and how long it ran before failing.
- **Changes:** fork, branch, and open a PR using the template. For anything non-trivial, open an issue first so we can agree on direction.
- **Security problems:** don't open a public issue. See [SECURITY.md](SECURITY.md).

## Before you push
Repos use pre-commit hooks for secret and personal-data scanning:
```bash
make setup        # installs the hooks
make test
```
Don't commit logs containing IMEI/IMSI/ICCID numbers, phone numbers, keys, or public IP addresses. Run `python3 tools/scrub.py --in-place <file>` on them.

## Hardware-related changes
If your change affects high voltage, RF power, or stored energy, say so in the PR and cite the datasheets or references you checked. It won't be merged without review against them.

## Expectations
These are personal projects. See [SUPPORT.md](SUPPORT.md) for what to expect in terms of response.
