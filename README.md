# Data repository for Hyperobjekt DDK project

To publish a new version of the data:

1. Add the new data files. Be sure to add the files to the appropriate type directory, `county`, `state`, `tract`, or `zip`.
2. The data processor assumes the following directory structure `shapetype > [index/pop/raw/zscores] > [index/pop/raw/zscores].csv`. For example: 
```
tract
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
state
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
2. Commit new data files to `master`.
2. Tag the commit and increment the version number, using [semantic versioning](https://semver.org/).
3. Push `master` to origin.
4. Merge `master` into `deploy` and push to origin.
