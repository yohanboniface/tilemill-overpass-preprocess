# tilemill-overpass-preprocess

When you want small dataset from overpass API. Very alpha.

# How to

Install `tilemill-overpass-preprocess`:

    npm install tilemill-overpass-preprocess

In the `mml` file, add a `table` attribute, with the overpass query, for example:

    …
    "Datasource": {
        "file": "/home/ybon/Downloads/montbrun-data/roads.geojson",
        "layer": "OGRGeoJSON",
        "table": "area[name='Montbrun-Bocage'][admin_level=8]->.zone;(way(area.zone)[highway];);(._;>;);out;"
    },
    …


Then run `./node_modules/tilemill-overpass-preprocess/bin/tilemill-overpass-preprocess yourprojectname`,
and every query will be run and the files created.

By default, existing files will not be overrided, add `--force` to force.
