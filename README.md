### Microburbs Property Orientation

Compute the facing orientation for each property using local road geometry.

#### What it does
- Loads listings with coordinates from `data/listings_domain.csv` (This was taken from a previous Uni project - raw dataset scraped from domain.com)
- Loads roads from `data/roads.gpkg`
- For each property point, finds its nearest road segment and computes the bearing from the road to the property
- Outputs each property with orientation in degrees and 8-way cardinal direction

#### Requirements
```bash
pip install -r requirements.txt
```

#### How to run
1) Just Run `property_orientation.ipynb`
2) Will write to `output/property_orientation.csv`


#### Output
- `output/property_orientation.csv` with columns including:
  - `lat`, `lon`
  - `orientation_degrees` (0 = North, clockwise)
  - `orientation_cardinal` (N, NE, E, SE, S, SW, W, NW)
  - `address` (when present in source)

#### Notes
- The notebook assumes Melbourne-area coordinates (WGS84) 
