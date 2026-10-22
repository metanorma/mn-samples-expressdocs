source "https://rubygems.org"

# SUMA E2E demo ladder — mirrors the proven local-iteration resolution
# (metanorma/iso-10303 Gemfile.lock), with two suma-line additions:
#   * suma from main-line git: render reuse, site freshness, incremental
#     builds, --no-valid, GCR/URN/provenance flows
#   * metanorma at the indirect-biblio anchor-dup fix (metanorma#613):
#     hidden copies of internal bibitems kept their anchor, tripping
#     metanorma-iso's id-uniqueness validation on collection renders
# Every ref below is pushed; nothing is path-pinned.

gem "suma", "0.5.10"

gem "metanorma", github: "metanorma/metanorma", branch: "main"
gem "metanorma-cli", github: "metanorma/metanorma-cli", branch: "main"
gem "metanorma-document", github: "metanorma/metanorma-document", branch: "main"
gem "metanorma-core", github: "metanorma/metanorma-core", branch: "main"
gem "metanorma-standoc", github: "metanorma/metanorma-standoc", branch: "main"
gem "metanorma-iso", github: "metanorma/metanorma-iso", branch: "add/iso-theme"
gem "metanorma-plugin-lutaml", "0.7.54"
gem "pubid", github: "pubid/pubid", branch: "main"
gem "expressir", github: "lutaml/expressir", branch: "fix/validate-remarks-duplication"

# proven resolution pins (newer releases break the stack; see each note)
gem "isodoc", "3.7.3"
gem "plurimath", "0.11.8" # 0.11.12 hangs on ISO 10303-41 AsciiMath
gem "relaton", "3.0.0.pre.alpha.4" # alpha.5+ rebinds YAML to the yeptris gate
gem "relaton-bib", "2.1.9"
gem "relaton-render", "1.3.0" # 3.x dropped Relaton::Render::Parse
gem "leptris", "1.9.379.1"
gem "yeptris", "0.6.26.2" # 0.6.35 Psych gate rejects ruby/range resources

gem "sassc-embedded", "~> 1.0"
