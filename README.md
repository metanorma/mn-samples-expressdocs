# mn-samples-expressdocs

A fictitious, wg12-shaped ISO 10303 STEP repository used as a static
test fixture for the metanorma stack: 10 synthetic modules and 3
synthetic resource documents (28 EXPRESS schemas, 13 documents),
renderable end-to-end with `suma build` in about 3 minutes.

Everything is generated and prose-free by construction: seeded
pseudo-random names and text, reserved fictitious part numbers
(10303-9xxx / 10303-99x), no ISO content of any kind. Redaction
reviewed in metanorma/iso-10303#725. See [PROVENANCE.md](PROVENANCE.md)
for the regeneration identity and the content-change policy.

## Layout

| Path | Role |
|---|---|
| `schemas/` | 28 EXPRESS schemas (annotated, wg12-shaped) |
| `documents/` | 13 resource/module documents (adoc sections + collection manifests) |
| `data/` | stepmod-layout mirror of the schemas (what `eengine -stepmod` resolves) |
| `metanorma.yml` | site manifest — build entry point |
| `collection-corpus.yml` | collection manifest (13 docrefs) |

## Build

```sh
metanorma site generate
```

or with the suma workflow:

```sh
bundle exec suma build metanorma.yml
```

## CI

The generate workflow builds the corpus on Ubuntu, Windows, and macOS
on every push and publishes the site as per-OS artifacts. The
gems-test workflow hooks into the metanorma release gate: a
metanorma/metanorma-* repository dispatch runs this corpus against the
changed gems, so template and rendering regressions surface here on a
3-minute build instead of a 2-hour one.

## Credits

The corpus model, generators, and redaction discipline were contributed
to the Metanorma project by Thomas Thurman (EXPRESS Language
Foundation) — TCSC410303-2745. Copyright Ribose Inc.; licensed BSD
3-Clause, see [LICENSE](LICENSE).
