# Sicily: law history in git

The law of the autonomous region of Sicily (Regione Siciliana, Italy) as a git history: one file per article, one commit per change, dated the day it took effect. `git blame` names the law behind every paragraph; `git log` lists every change to an article; checking out a date gives the text in force that day (here: the text in force when it was retrieved).

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `it-82/`. Italy's national law is in [lexifina/italy-law](https://github.com/lexifina/italy-law).

The text is in Italian, exactly as the source prints it.

## What this repository holds

1 act with 1 version so far: the Statute of Autonomy (a constitutional law of the Italian State) first, then the regional laws in force, added in parts of about fifty.

| Folder | Act | Versions | History |
| --- | --- | ---: | --- |
| `statuto/` | Statuto speciale della Regione Siciliana | 1 | oldest version available: 30 October 2026 |

## Source

The Statute of the Sicilian Region (Statuto speciale della Regione Siciliana: R.D.Lgs. 15 maggio 1946, n. 455, converted into legge costituzionale 26 febbraio 1948, n. 2, and amended by the constitutional laws of 1972, 1989, 2001 and 2013) as the Assemblea Regionale Siciliana publishes it on <https://www.ars.sicilia.it/statuto-della-regione>: a PDF of June 2019 extracted from the ARS volume "Regolamento interno dell'Assemblea", read from its text layer, with the ARS's footnotes. The running header and page numbers are left out; words the PDF hyphenates at a line end are joined.

## Dates

- Each act's text is the consolidated text in force on the retrieval day (30 October 2026), as the Assemblea Regionale Siciliana (ARS) publishes it. The source gives no dated past versions, so each act has one commit, its **oldest version available**, dated at **noon, Europe/Rome, on 30 October 2026** and credited to the Assemblea Regionale Siciliana (ARS) as publisher, naming the act itself.
- This is not the date the text took effect: it is the day the text was read. Earlier wordings are not in this record.
- Versions that take effect after the retrieval day are on the `futuro` branch, never merged into `main`.

## Files

`statuto/art-001.md` is Articolo 1 of the Statute; `intestazione.md` holds the title page and the list of the acts that approved and amended it. The headings of titles and sections stay in the file of the article they stand before, and the ARS's footnotes in the file of the page text they follow (a note number printed after an article number, as in "Art. 33", is the note mark of Art. 3). One paragraph per line.

## How it is checked

- Every version of every act is read back from git on the day it took effect and on the day before (`tools/check_repo.py`); both must match `corpus.json`.
- The letters and digits of every version equal those of the Assemblea Regionale Siciliana (ARS)'s own text of that version (read by a second, independent reader), and every unit's text appears in it in order.
- Health checks: no merge commits, commit dates never go backwards, nothing dated in the future, and every commit's trailers parse.

## What "author" means

Every commit here is an "oldest version available" commit, authored by the publisher, the Assemblea Regionale Siciliana (ARS), with an e-mail address that cannot exist. The committer is always Lexifina.

## Limits

This is not an official publication. The binding text of the Statute is the one published in the Gazzetta Ufficiale; the ARS PDF is a reading copy. Only the current text of each act is recorded, not its earlier wordings. Only the acts listed above are included.
