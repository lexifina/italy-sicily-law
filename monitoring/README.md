<!-- lawwatch: written from data/checks by the check trail; edit the records, not this page -->

# Monitoraggio: che cosa si legge e con quale esito

[English](README.en.md)

Come global-law monitora ogni paese: [global-law monitoring/](https://github.com/lexifina/global-law/tree/main/monitoring). Questa pagina fa lo stesso per Sicilia soltanto: ogni lettura di una fonte ufficiale, quando è avvenuta e con quale esito (atti aggiunti, modificati e rimossi). La forma leggibile dalle macchine è [data/checks/](../data/checks/) (JSON Lines, schema `lexifina-check/1`), in `git log` come commit `Kind: check`, e mese per mese in [checks/](checks/).

**Ultimo controllo:** 2026-11-24 00:30 UTC, Assemblea Regionale Siciliana: 4 indirizzi letti; 0 aggiunti, 0 modificati, 0 rimossi; nessuna modifica; 0 non pubblicati, di cui 0 senza motivo.

## Fonti

| Fonte | Cartelle | Frequenza | Ultimo controllo riuscito | Ultimo esito | Stato |
| --- | --- | --- | --- | --- | --- |
| [Assemblea Regionale Siciliana](https://www.ars.sicilia.it/statuto-della-regione) | `statuto/` | ogni giorno | 2026-11-24 00:30 UTC | nessuna modifica | sorvegliata: il repository contiene solo lo Statuto: la banca dati delle leggi regionali dell'ARS mostra i testi sotto /icaro/, che il suo robots.txt esclude, quindi le leggi regionali non sono lette |

## Gli ultimi 30 giorni

| Inizio (UTC) | Fonte | Letti | Aggiunti | Modificati | Rimossi | Non pubblicati (senza motivo) | Esito | Commit |
| --- | --- | ---: | ---: | ---: | ---: | ---: | --- | ---: |
| [2026-11-24 00:30](checks/2026-11.md#it-ars-20261124t003045z) | ars | 4 | 0 | 0 | 0 | 0 (0) | nessuna modifica | — |

## Verificalo da te

```
python tools/checktrail.py                      # l'ultimo controllo di ogni fonte
python tools/checktrail.py --day 2026-11-23     # tutti i controlli di un giorno
python tools/checktrail.py --act <id>           # quando un atto è stato visto e pubblicato
git log --grep='^Kind: check' --format='%ci %s'  # i controlli nella cronologia
```

Ha valore legale solo la pubblicazione ufficiale; i testi qui sono copie per la lettura e la ricerca.
