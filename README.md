# Assistant check: fingerprints

RunselfHQ is testing customer-facing AI assistants on an invented clinic: the same AI model, with
and without our rules. Part of the test questions is sealed before our rules are written. This
repo posts their fingerprints in advance, so anyone can later check that the questions were not
changed, or chosen after seeing results.

## How to check
After the published run we publish the salt and the sealed file. Then run:

    { printf '%s' "<salt>"; cat sealed-questions.json; } | shasum -a 256

The result must equal that share's fingerprint below, posted on the date shown.

## Fingerprints
| Posted (UTC) | What | Salted SHA-256 |
|---|---|---|
| 2026-10-29 | Sealed question share 1, 17 questions (retired 2026-10-29, see below) | 2c451cf0eab53f0071513a3692a6e7a1033e4e2708ed164a629b0a1d9783ef35 |
| 2026-10-29 | Sealed question share 2, 17 questions (replaces share 1) | c25a3dcdb660cd8de0873c657ef855d32deed69b1845aadf377643d1a2c8c06b |

## Changes
- 2026-10-29: share 1 retired before any run. A build worker's search reached the folder that held it, and it reused wording that was visible to the builders. Share 2 was written afresh and checked for overlap; both shares and their salts are published after the run.
