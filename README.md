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
| `metanorma-corpus.yml` | site manifest — build entry point |
| `collection-corpus.yml` | collection manifest (13 docrefs) |

## Build

```sh
bundle install
bundle exec suma build metanorma-corpus.yml
```

## CI

The build workflow compiles the corpus on every push and weekly
against metanorma main: the corpus doubles as a stack canary — if a
metanorma/suma change breaks real-world collection rendering, it
breaks here first, on a 3-minute build instead of a 2-hour one.
`expressir validate remarks` gates the source: a block anchor
(`[[name]]`) may be defined in only one remark scope per schema.
