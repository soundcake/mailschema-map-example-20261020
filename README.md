# Mail Action Protocol 0.3 example

This repository contains an original Account Security Response description validated with `mailschema` 0.3.2.

- [`description.json`](description.json) — the validated description
- [`report.md`](report.md) — reproducibility and negative-check notes
- [`contract.json`](contract.json) — the pinned Account Security Response 0.1 contract used for validation

Validate it with:

```sh
pnpm install --frozen-lockfile
node node_modules/mailschema/bin/mailschema.js description description.json --contract contract.json
```
