# Tempo day colours since 2014: daily dataset

Daily colour (blue, white or red) of the French **Tempo** electricity tariff, from **1 September 2014** to the latest
announced day, as published by **RTE**, the French transmission system operator. Compiled and kept up to date by
[Jour Tempo](https://jourtempo.fr/).

*Version française plus bas.*

- File: [`data/tempo-historique.csv`](data/tempo-historique.csv)
- Live version (updated every day): https://jourtempo.fr/api/v1/tempo-historique.csv
- Documentation of the free API: https://jourtempo.fr/api/
- Also listed on data.gouv.fr: https://www.data.gouv.fr/datasets/historique-des-couleurs-tempo-depuis-2014-jours-bleus-blancs-et-rouges

Each release of this repository is an archived, citable snapshot of the file. The live file above is the one to use
for current data.

## Columns

One line per day, comma separated, UTF-8, header on the first line.

| Column | Format | Content |
| --- | --- | --- |
| `date` | `YYYY-MM-DD` | Tempo day. A Tempo day runs from 06:00 to 06:00 the next day (Paris time). |
| `couleur` | `bleu`, `blanc` or `rouge` | colour of the day: blue, white or red |
| `saison` | `YYYY-YYYY` | Tempo season, from 1 September to 31 August |

```
date,couleur,saison
2014-09-01,bleu,2014-2015
```

## Content of this version (16 October 2026)

4,430 days, 2014-09-01 to 2026-10-17: 12 complete seasons (2014-2015 to 2025-2026) and the current season
2026-2027 up to the last announced day. No missing day, no unknown value.

| Season | Blue | White | Red | Days |
| --- | --- | --- | --- | --- |
| 2014-2015 | 300 | 43 | 22 | 365 |
| 2015-2016 | 301 | 43 | 22 | 366 |
| 2016-2017 | 300 | 43 | 22 | 365 |
| 2017-2018 | 300 | 43 | 22 | 365 |
| 2018-2019 | 300 | 43 | 22 | 365 |
| 2019-2020 | 301 | 47 | 18 | 366 |
| 2020-2021 | 300 | 43 | 22 | 365 |
| 2021-2022 | 300 | 43 | 22 | 365 |
| 2022-2023 | 300 | 43 | 22 | 365 |
| 2023-2024 | 301 | 43 | 22 | 366 |
| 2024-2025 | 300 | 43 | 22 | 365 |
| 2025-2026 | 300 | 43 | 22 | 365 |
| 2026-2027 (in progress) | 47 | 0 | 0 | 47 |

## Source and method

- **Source**: colours set and published by RTE through its official data interface, API "Tempo Like Supply Contract"
  (https://data.rte-france.com). The history starts with the 2014-2015 season, the first one available there.
- **Collection**: Jour Tempo reads the RTE interface six times a day (06:05, 11:00, 11:30, 12:00, 12:30 and 18:00,
  Paris time). If it is unavailable, an independent source is used as a fallback; it was cross-checked against RTE
  with no difference over the 2023 to 2026 seasons.
- **Checks**: one line per calendar day with no gap, colour limited to the three codes, season derived from the date.
  The yearly counts above are computed from the file itself.

## Limits

- The current season is incomplete; its last line can be tomorrow once RTE has announced it (around 10:30).
- Colours are copied as published. If RTE corrects a past day, the live file is corrected and the next release
  carries the correction; earlier releases stay unchanged.
- The 2019-2020 season counts 18 red and 47 white days, against 22 and 43 in the other seasons: this is what the
  source shows, not a gap in the file.
- This dataset says nothing about prices. Jour Tempo is independent: neither EDF nor RTE.

## How to cite

> Jour Tempo, *Tempo day colours since 2014-2015 (daily dataset)*, from RTE public data (API Tempo Like Supply
> Contract). Version [version], [DOI]. https://jourtempo.fr/api/v1/tempo-historique.csv

The DOI of each version is shown on its Zenodo page. GitHub also offers a "Cite this repository" button
(from `CITATION.cff`).

## Licence

Data under **Licence Ouverte 2.0 (Etalab)**, see [LICENSE](LICENSE). Tempo colours come from RTE, whose terms of use
(data.rte-france.com, article 9) allow reuse provided the source is credited. Credit to display:
**"Couleurs Tempo : RTE, via Jour Tempo (https://jourtempo.fr)"**.

Contact: contact@jourtempo.fr

---

## En français

**Historique des couleurs Tempo depuis 2014** : une ligne par jour, du 1er septembre 2014 au dernier jour annoncé,
avec la date, la couleur (`bleu`, `blanc`, `rouge`) et la saison (du 1er septembre au 31 août). Un jour Tempo va de
6 h à 6 h le lendemain (heure de Paris).

- Source : couleurs publiées par **RTE** (API Tempo Like Supply Contract, data.rte-france.com), relevées six fois par
  jour par Jour Tempo ; en secours, une source indépendante, contre-vérifiée sans écart sur les saisons 2023 à 2026.
- Cette version (16 octobre 2026) : 4 430 jours, 12 saisons complètes (2014-2015 à 2025-2026) et la saison
  2026-2027 en cours. Aucun jour manquant.
- Fichier à jour chaque jour : https://jourtempo.fr/api/v1/tempo-historique.csv ; documentation de l'API gratuite :
  https://jourtempo.fr/api/ ; fiche data.gouv.fr :
  https://www.data.gouv.fr/datasets/historique-des-couleurs-tempo-depuis-2014-jours-bleus-blancs-et-rouges
- Chaque version (*release*) de ce dépôt est archivée sur Zenodo avec son propre DOI, pour citer une version figée.
- Limites : saison en cours incomplète ; une correction de RTE sur un jour passé n'apparaît que dans les versions
  suivantes ; 2019-2020 compte 18 jours rouges et 47 blancs, comme dans la source.
- Licence : **Licence Ouverte 2.0 (Etalab)**. Crédit à afficher : **« Couleurs Tempo : RTE, via Jour Tempo »**, avec
  un lien vers https://jourtempo.fr. Jour Tempo est un site indépendant, ni EDF ni RTE.
