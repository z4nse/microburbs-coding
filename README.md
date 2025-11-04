### Microburbs Property Orientation

Compute the facing orientation for each property using local road geometry.

#### What it does
- Loads properties from `data/gnaf_prop.parquet`
- Loads roads from `data/roads.gpkg`
- For each property point, finds its nearest road segment and computes the bearing from the road to the property
- Outputs each property with orientation in degrees and 8-way cardinal direction

#### Requirements
```bash
pip install -r requirements.txt
```

#### To run:
1) Run `property_orientation.ipynb`
   - First cell previews `data/roads.gpkg` coverage
   - Then run the rest (config, load, compute, and summaries)
2) Writes:
   - `output/property_orientation.csv`

#### Inputs
- `data/gnaf_prop.parquet`
- `data/roads.gpkg`


#### Output
- `output/property_orientation.csv` with columns including:
  - `lat`, `lon`
  - `orientation_degrees` (0 = North, clockwise)
  - `orientation_cardinal` (N, NE, E, SE, S, SW, W, NW)

#### Notes
- CRS handled as WGS84 internally; properties are filtered to the bounding box of `roads.gpkg` before computation
