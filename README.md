# tournament-tracker
A simple .html tournament tracker

## Versioning
The version is set in one place only: `VERSION` and `BUILD_DATE` at the top of the script in `index.html`.
- The footer shows it.
- The offline cache in `sw.js` is named after it, so installed apps load the new version.
- After a merge to `main`, the workflow `.github/workflows/tag-version.yml` creates the tag `v<VERSION>` if it does not exist yet.

Raise the version with every change that should get its own tag.

## Stats edition (`stats/`)
A second app at `<site>/stats/`, next to the main app, which stays unchanged. It adds:
- a **Players** tab with a fixed player pool; the Teams tab only picks players from it,
- a colour per team,
- **Save to stats** under Table once all scores are in. Saved tournaments are snapshots; every number is worked out from them, so saving a corrected tournament again replaces it instead of counting twice,
- per player: tournaments, matches and the goals of their team (for and against), finals included,
- per colour, just for fun: wins, draws, losses, Cups and Plates.

Both apps share the origin, so the stats edition uses its own storage keys (`sexyfc-stats-*`) and its own offline cache, and only reads the main app's tournament once, on its first start. Tournament backups work in both directions. The stats database has its own backup under Players.

Its version is `VERSION` in `stats/index.html`; the workflow tags it as `stats-v<VERSION>`.
