# leaflet-map-polygon-hover
Leaflet thematic polygon (choropleth) map, with hover info window, using GeoJSON data

## My Demo
http://stacylam9.github.io/leaflet-map-polygon-hover/index.html

## Jack's Demo
- http://jackdougherty.github.io/leaflet-map-polygon-hover/index.html

## Compare with
- similar version that draws data from a .js file with declared variable
- http://github.com/jackdougherty/leaflet-map-polygon-hover-from-js/index.html

## Advantage
- This GeoJSON version is simpler for novices to understand, since they can create and join GeoJSON data file in MapShaper.org

## Credits
- Leaflet choropleth tutorial (with US state population density example): http://leafletjs.com/examples/choropleth.html
- solved reset highlight problem http://stackoverflow.com/questions/30524035/geojson-getjson-and-remove-higlight-mouse-out-on-leaflet

## Create your own

See chapter tutorials in http://DataVizForAll.org

####General overview of steps below
- Join a GeoJSON polygon map with spreadsheet data
- Modify color ranges and info box text & variables as needed
- Upload all files to a forked or new GitHub repository, create GitHub pages branch for live web host

####Detailed steps:
- Start with GeoJSON polygon map with no numerical data, such as: ct-towns-borders.geojson
- Import polygon map into http://MapShaper.org. Simplify to reduce size as needed.
- Export as CSV to create spreadsheet of polygon names. In this example, column header is "town"
- Open CSV with any spreadsheet tool. Insert columns of data into the CSV sheet. Use VLOOKUP function if needed.
- Save CSV with new name: ct-towns.csv
- Import ct-towns.csv as second layer into MapShaper.org.
- Use the drop-down to select the polygon map (ct-towns-borders.geojson) as the active, displayed layer.
- Click the Console and enter command to join the CSV table to the GeoJSON polygon
  ```
  -join ct-towns.csv keys=town,town
  ```
- Export the newly joined map with a new filename in GeoJSON format: ct-towns-density.json)
- Change the file name suffix from .json to .geojson to avoid confusion
- Fork this GitHub repository, or create your own, with these files (or equivalent):
  - index.html
  - script.js
  - style.css
  - ct-towns-density.geojson  (the data file)

- in index.html, adjust the reference to the data file
- in script.js, adjust the hover info box text and references as needed
- in script.js, Adjust the ranges with http://colorbrewer.org
