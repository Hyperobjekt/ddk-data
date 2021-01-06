# Data repository for Hyperobjekt DDK project

To publish a new version of the data:

1. Add the new data files. Be sure to add the files to the appropriate type directory, `counties`, `states`, `tracts`, or `zips`.
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
  - `./states/StateFips/Usps.csv`
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
4. Merge `master` into `deploy` and push to origin.
