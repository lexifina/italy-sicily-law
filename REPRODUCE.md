# How this repository was made (Sicily)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Assemblea Regionale Siciliana | <https://www.ars.sicilia.it/statuto-della-regione> | 2026-10-30 | L. 633/1941 art. 5: official acts are not protected. The ARS site states no restriction on reusing the texts. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `statuto` | Statuto speciale della Regione Siciliana | 1 | 2026-10-30 to 2026-10-30 |

The build made 1 commits:

| Commits | Kind |
| ---: | --- |
| 1 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 1 tags.

## Dates

Each commit is dated at noon (Europe/Rome) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Statuto della Regione Siciliana, art. 29: regional laws are published in the Gazzetta Ufficiale della Regione; the general rule (preleggi art. 10) is entry into force on the fifteenth day after publication unless the law says otherwise. (Not applied here: the text is the current one, dated the retrieval day.) https://www.ars.sicilia.it/statuto-della-regione

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `8fac882e5a77baab342dba7634ed503ba81bd47b1ff97bc21daecd689488dea3` (33679 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a97ff7ea62c3c7595c5668a297d533da0b74373c`, `check.py` `3e59cb6f05eccb94a9ec14431a7f6781221e83ef`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

1 versions of 1 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Current-only: the Statute as the ARS publishes it (PDF of June 2019), one "oldest version available" commit dated the retrieval day, naming legge costituzionale 1948, n. 2.
- Paragraphs are rebuilt from the PDF's lines: the running header "STATUTO DELLA REGIONE" and page numbers are left out, words hyphenated at a line end are joined; footnotes stay where the PDF prints them. An article number with a note mark glued to it ("Art. 33") is read as the next article in sequence (Art. 3).
- Regional laws are not included.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- A model (Claude) wrote the parse code; it wrote no law text. Every word comes from the ARS PDF.
