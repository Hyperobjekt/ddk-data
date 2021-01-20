# Data repository for Hyperobjekt DDK project

To publish a new version of the data:

1. Check out the `master` branch (or create a branch of `master` that you will merge back into `master`).
2. Drop in the updated data files. Be sure to add the files to the appropriate type directory, `counties`, `states`, `tracts`, or `zips`.
3. The data processor assumes the following directory structure `shapetype > [index/pop/raw/zscores] > [index/pop/raw/zscores].csv`. For example:
```
tracts
  index
    dictionary.csv
    index.csv
    resource_metadata.csv
  pop
    dictionary.csv
    pop.csv
    resource_metadata.csv
  raw
    dictionary.csv
    raw.csv
    resource_metadata.csv
  zscores
    dictionary.csv
    zscores.csv
    resource_metadata.csv
states
  index
    dictionary.csv
    index.csv
    resource_metadata.csv
  pop
    dictionary.csv
    pop.csv
    resource_metadata.csv
  raw
    dictionary.csv
    raw.csv
    resource_metadata.csv
  zscores
    dictionary.csv
    zscores.csv
    resource_metadata.csv
...
```
4. Exceptions to the above structure include:
  - `./states/StateFipsUsps.csv`
  - The barcharts directory, which assumes the following paths:
  ```
  barcharts
    msaname15.csv
    nation.csv
    stateusps.csv
  ```
5. Commit your changes and merge them back into master. Push `master` to `origin`.
6. Tag the commit and increment the version number, using [semantic versioning](https://semver.org/). :fire::fire::fire: **Be careful.** Pushing a new version triggers a new data build (for Mapbox tilesets and all other data loaded by the app). :fire::fire::fire:
```bash
git tag # list local tags
git tag 1.0.3 # add a tag, don't put a "v" at the beginning
git push origin 1.0.3 # push your local tag to remote
```

## Docker Configuration

For `.env` configuration, which is done in `.github/workflows/master.yml`, review the [README for the ddk-etl repository](https://github.com/Hyperobjekt/ddk-etl).
