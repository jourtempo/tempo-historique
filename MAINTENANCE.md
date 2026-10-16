# Maintenance

One release per completed season, on **1 September** (the day a new Tempo season starts). Each GitHub release is
archived by Zenodo with its own DOI; the concept DOI (all versions) stays the same.

## Every 1 September

1. Replace `data/tempo-historique.csv` with the live file:
   https://jourtempo.fr/api/v1/tempo-historique.csv
2. Check it: the season that ended on 31 August has 365 or 366 lines, no day is missing, colours are only `bleu`,
   `blanc`, `rouge`. Quick check (Python 3, no package needed):

   ```
   python -c "import csv,collections as c;r=list(csv.DictReader(open('data/tempo-historique.csv',encoding='utf-8')));print(len(r),r[0]['date'],r[-1]['date']);print(sorted(c.Counter((x['saison'],x['couleur']) for x in r).items())[-6:])"
   ```

3. In `README.md`: update the "Content of this version" section (date, number of days, last date) and add the line of
   the completed season to the table. Same for the French section.
4. In `CITATION.cff`: set `version` and `date-released` to the release date (`YYYY-MM-DD`).
5. Commit, then create a GitHub release:
   - tag: the completed season, for example `2026-2027`;
   - title: `Season 2026-2027 complete`;
   - notes: number of days, counts of the completed season, any correction of past days.
6. Check on Zenodo that the new version appears (a few minutes) and that the licence is "Etalab Open License 2.0".

## Corrections

If RTE corrects a past day, the live file is corrected. Publish an extra release only if the correction matters for
users (say which day changed in the release notes); otherwise wait for 1 September.

## Contact

contact@jourtempo.fr
