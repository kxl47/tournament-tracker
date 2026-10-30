# tournament-tracker
A simple .html tournament tracker

## Versioning
The version is set in one place only: `VERSION` and `BUILD_DATE` at the top of the script in `index.html`.
- The footer shows it.
- The offline cache in `sw.js` is named after it, so installed apps load the new version.
- After a merge to `main`, the workflow `.github/workflows/tag-version.yml` creates the tag `v<VERSION>` if it does not exist yet.

Raise the version with every change that should get its own tag.
