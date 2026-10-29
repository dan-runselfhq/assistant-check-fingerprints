# Assistant check: fingerprints

RunselfHQ is testing customer-facing AI assistants on an invented clinic: the same AI model, with
and without our rules. Part of the test questions is sealed before our rules are written. This
repo posts their fingerprints in advance, so anyone can later check that the questions were not
changed, or chosen after seeing results.

## How to check
After the published run we publish the salt and the sealed file. Then run:

    { printf '%s' "<salt>"; cat sealed-questions.json; } | shasum -a 256

The result must equal the fingerprint below, posted on the date shown.

## Fingerprints
| Posted (UTC) | What | Salted SHA-256 |
|---|---|---|
| 2026-10-29 | Sealed question share, 17 questions | 2c451cf0eab53f0071513a3692a6e7a1033e4e2708ed164a629b0a1d9783ef35 |
