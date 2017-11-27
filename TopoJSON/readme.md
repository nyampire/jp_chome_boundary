Convert chome boundary from ShapeFile to TopoJSON

  ```bash
  export SHAPE_ENCODING=CP932
  for file in `\find . -name '*.shp'`; do
      ogr2ogr -s_srs EPSG:4612 -t_srs EPSG:4326 -lco COORDINATE_PRECISION=7 -f geoJSON ${file%.*}.geojson $file
      topojson --no-quantization -p -o ${file%.*}.topojson ${file%.*}.geojson
  done
  ```
