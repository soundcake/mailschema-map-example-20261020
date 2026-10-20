# MailSchema account security response validation notes

- Environment: macOS arm64, Node.js `v24.19.0`, pnpm `11.25.0`, and `mailschema` `0.3.2`.
- I installed with `pnpm add mailschema@0.3.2 --save-exact`, downloaded the Account Security Response 0.1 contract from the MAP 0.3 Registry, then ran `node node_modules/mailschema/bin/mailschema.js description description.json --contract contract.json`.
- It took about four minutes from the completed install to a valid description. The CLI reported `sha-256:1ef965ed96b1239dead6cad0658e8456d69fc2485269be4c61584a7dd577bdeb`.
- For the negative check, I changed `details.event.occurredAt` from a UTC timestamp ending in `Z` to the equivalent `+00:00` form. The exact error was `/details/event/occurredAt: must match pattern "^\d{4}-\d{2}-\d{2}T\d{2}:\d{2}:\d{2}Z$"`.
- The slowest step was locating the example linked from the Registry page and distinguishing the description digest from the contract digest.
- I found no package defect after checking the README, CLI help, Registry contract, one valid run, and the deliberate invalid run.
- I would add a copy-ready validation command beside each Registry example so the contract URL and expected workflow are visible together.
