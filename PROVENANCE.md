# PROVENANCE

Every file in this repository is generated output. Nothing here is ISO
content: all names, prose, identifiers, and part numbers are fictitious
(reserved bands 10303-9xxx for modules, 10303-99x for resources), and
the corpus passed redaction review in metanorma/iso-10303#725
(2026-08-16).

## Regeneration identity

| Input | Value |
|---|---|
| Generator | `generate-corpus.py` v0.2.0, wg12-step branch `corpus/TCSC410303-2745-synthetic-corpus` (TCSC410303-2745) |
| Seed | `1` |
| Profile | `corpus-profile.ref.json` (cp-1) from metanorma/iso-10303#725 |
| Scale plan | `scale-plan.json` (sp-1) from metanorma/iso-10303#725 |

Generation is deterministic: the same (seed, profile, scale-plan)
yields a byte-identical tree. The generators live upstream in the
wg12-step repository; **this repository is frozen output** — it never
contains the Python tooling, and content changes here mean one of two
things only:

1. a deliberate re-generation upstream (recorded here with the new
   generator identity), or
2. a hand-applied fix to a fixture (recorded in the commit message and
   mirrored upstream so the generator reproduces it).

## Consumed by

- The metanorma release gate: metanorma/metanorma-* repository
  dispatches run this corpus against the changed gems (see
  `.github/workflows/test.yml`), so template and rendering regressions
  surface here first.
- `metanorma diff` / verify-changes conformance (upstream, wg12-step
  TCSC410303-2745) uses these trees as its static test corpus.

## Build

```sh
metanorma site generate
```

or `bundle exec suma build metanorma.yml` with the suma workflow.

Requires ~2 GB RAM, ~3 minutes. Outputs `site/` or `_site/` (gitignored).
