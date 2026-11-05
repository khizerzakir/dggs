### To Enable Pixi Env

If it isn't detected automatically, you can manually select the interpreter (e.g. .pixi/envs/default/bin/python) via the Python: Select Interpreter command in the Command Palette.

### CARTO basemap

Set the CARTO API key in the shell before starting Jupyter:

```bash
export CARTO_API_KEY="your-carto-api-key"
pixi run jupyter lab
```

The notebook reads `CARTO_API_KEY` without storing it in the notebook. If it is
not visible to the notebook kernel, rerun the CARTO setup cell and enter the key
when prompted. If it is not set, the Folium map uses OpenStreetMap tiles as a fallback. Use the map's
layer control to toggle the ISEA4T polygons, ISEA7H centroids, ISEA7H extent
polygons, ISEA7H point cells, ISEA4H point cell IDs, and the overview grid.

If a key was previously pasted into the notebook, revoke it in CARTO and create
a replacement; the notebook must never contain or print the key.

The interactive map intentionally embeds sampled and simplified display layers
only. The complete-resolution GeoJSON files are still written by the notebook,
but are not embedded into the HTML because doing so makes Folium slow and
memory-heavy.