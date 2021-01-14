# Data repository for Hyperobjekt DDK project

To publish a new version of the data:

1. Check out the `master` branch (or create a branch of `master` that you will merge back into `master`).
1. Drop in the updated data files. Be sure to add the files to the appropriate type directory, `counties`, `states`, `tracts`, or `zips`.
2. The data processor assumes the following directory structure `shapetype > [index/pop/raw/zscores] > [index/pop/raw/zscores].csv`. For example:
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
3. Exceptions to the above structure include:
  - `./states/StateFipsUsps.csv`
  - The barcharts directory, which assumes the following paths:
  ```
  barcharts
    msaname15.csv
    nation.csv
    stateusps.csv
  ```
2. Commit new data files to `master`.
2. Tag the commit and increment the version number, using [semantic versioning](https://semver.org/).
3. Push `master` to origin.
4. Merge `master` into `trigger-deploy` and push to origin. :fire::fire::fire:**Be careful.** Pushing to `trigger-deploy` triggers a new data build (for Mapbox tilesets and all other data loaded by the app) using the tag as the data version.  So if you push the new data without updating the tag it will overwrite the tilesets and data files for the current version (which might be in use by the staging or production sites).:fire::fire::fire:
